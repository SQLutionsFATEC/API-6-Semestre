# A6-24 – Integration Tests

## 1. Purpose

This document complements the project's existing test documentation by describing the DevOps implementation introduced for card **A6-24 - [DEVOPS] Integration Tests**.

The objective is to provide a standardized process for running automated tests in isolated environments, generating test reports, executing the test suites automatically through GitHub Actions, and integrating the results with SonarCloud.

The existing test documentation defines the project's testing principles, test layers, naming conventions, code review practices, and basic test commands. This document focuses on the infrastructure and automation required to execute those tests consistently.

---

## 2. Scope

The A6-24 implementation covers the following project components:

| Component    | Main technologies          | Test solution                                       |
| ------------ | -------------------------- | --------------------------------------------------- |
| Backend      | Django, Python, PostgreSQL | pytest, pytest-django, pytest-cov, Docker           |
| Frontend     | React, JavaScript/JSX      | Vitest, React Testing Library, jsdom, V8            |
| CI/CD        | GitHub Actions             | Automated lint, tests, coverage, build and analysis |
| Code quality | SonarCloud                 | Static analysis, coverage and Quality Gate          |

The implementation is divided between the Backend and Frontend repositories, which are part of the main `API-6-Semestre` project.

---

## 3. Backend Integration Test Environment

### 3.1 Overview

The Backend integration test environment runs inside Docker and uses an isolated PostgreSQL database.

This prevents the test suite from depending on the developer's local database and provides a reproducible environment for local execution and CI/CD.

The test environment contains two services:

```text
postgres-test
      ↓
backend-test
```

The `postgres-test` service provides the PostgreSQL database.

The `backend-test` service runs the Django migrations and executes the pytest test suite against the test database.

### 3.2 Configuration

The test environment is defined by:

```text
API-6-Semestre-Backend/deploy/docker-compose.test.yml
```

The Backend container is configured to connect to:

```text
DB_NAME=api_test_db
DB_USER=postgres
DB_PASSWORD=<test password>
DB_HOST=postgres-test
DB_PORT=5432
```

The PostgreSQL service includes a health check to ensure that the database is ready before the Backend tests start.

### 3.3 Local execution

From the Backend repository:

```bash
cd API-6-Semestre-Backend
```

Validate the Docker Compose configuration:

```bash
docker compose -f deploy/docker-compose.test.yml config
```

Build the test images:

```bash
docker compose -f deploy/docker-compose.test.yml build
```

Start the PostgreSQL test database:

```bash
docker compose -f deploy/docker-compose.test.yml up -d --wait postgres-test
```

Run the Backend test suite:

```bash
docker compose -f deploy/docker-compose.test.yml run --rm backend-test
```

Remove containers, networks and test volumes after execution:

```bash
docker compose -f deploy/docker-compose.test.yml down -v --remove-orphans
```

### 3.4 Database migrations

Before the tests are executed, the Backend container applies the Django migrations automatically:

```bash
python manage.py migrate --noinput
```

This ensures that the PostgreSQL test database has the schema required by the application.

The container entrypoint also preserves the project's optional seed mechanism through the `RUN_SEED` environment variable.

For the integration test environment, the seed is disabled:

```text
RUN_SEED=false
```

### 3.5 Test execution and reports

The Backend test command executes pytest with coverage and JUnit XML reporting:

```bash
python -m pytest api/tests/ -v \
  --cov=api \
  --cov-config=.coveragerc \
  --cov-report=term-missing \
  --cov-report=xml:coverage.xml \
  --junitxml=test-results.xml
```

The generated reports are:

```text
django/coverage.xml
django/test-results.xml
```

`coverage.xml` contains code coverage information.

`test-results.xml` contains the test execution results in xUnit format.

These reports are generated artifacts and must not be committed to the repository.

---

## 4. Frontend Automated Tests

### 4.1 Overview

The Frontend follows the testing model established in the project's existing documentation and uses Vitest together with React Testing Library for automated tests.

The A6-24 implementation added an executable test environment using:

* Vitest;
* React Testing Library;
* jsdom;
* `@testing-library/jest-dom`;
* V8 coverage.

### 4.2 Test configuration

The main configuration file is:

```text
API-6-Semestre-Frontend/vitest.config.js
```

The test environment uses:

```text
jsdom
```

and the V8 provider for coverage.

The test setup file is:

```text
API-6-Semestre-Frontend/src/test/setup.js
```

### 4.3 Tested components and pages

The A6-24 implementation added automated tests for:

```text
DocumentItem
DocumentList
DocumentModal
Pagination
SearchBar
Home
```

Tests follow the repository's `.test.jsx` naming convention.

### 4.4 Local execution

From the Frontend repository:

```bash
cd API-6-Semestre-Frontend
```

Install dependencies:

```bash
npm ci
```

Run the tests:

```bash
npm test
```

Run the tests with coverage:

```bash
npm run test:coverage
```

Run ESLint:

```bash
npm run lint
```

Run the production build:

```bash
npm run build
```

### 4.5 Coverage report

The coverage command generates:

```text
coverage/lcov.info
```

The LCOV report is configured for SonarCloud through:

```text
sonar-project.properties
```

The coverage configuration is defined in:

```text
vitest.config.js
```

The generated `coverage/` directory is excluded from version control.

---

## 5. GitHub Actions Automation

The A6-24 implementation moves test execution from a manual-only process to an automated CI/CD process.

The pipelines are triggered by repository changes and Pull Requests targeting the project's main development branches.

### 5.1 Backend workflow

The Backend integration test workflow is:

```text
API-6-Semestre-Backend/.github/workflows/sonar.yml
```

The workflow performs the following sequence:

```text
Checkout repository
        ↓
Build integration test images
        ↓
Start PostgreSQL
        ↓
Run Backend tests
        ↓
Generate coverage and test reports
        ↓
Validate generated reports
        ↓
Clean up Docker environment
        ↓
Run SonarCloud analysis
```

The PostgreSQL service is started with a health check before the Backend test container is executed.

The integration test environment is always removed at the end of the workflow, including failure scenarios.

### 5.2 Frontend workflow

The Frontend workflow is:

```text
API-6-Semestre-Frontend/.github/workflows/ci-frontend.yml
```

The workflow executes:

```text
Checkout repository
        ↓
Install dependencies
        ↓
Run ESLint
        ↓
Run tests with coverage
        ↓
Build production application
        ↓
Validate LCOV report
        ↓
Run SonarCloud analysis
```

This ensures that code changes are checked for test failures, lint problems, build failures and code quality issues before they are integrated into the target branch.

---

## 6. SonarCloud Integration

SonarCloud is integrated into the automated workflows to complement the execution of automated tests with static code analysis and coverage information.

### 6.1 Backend

The Backend pipeline generates:

```text
coverage.xml
test-results.xml
```

The workflow validates that these reports are generated successfully before the SonarCloud analysis is executed.

### 6.2 Frontend

The Frontend pipeline generates:

```text
coverage/lcov.info
```

The LCOV path is configured in:

```text
sonar-project.properties
```

with the following property:

```text
sonar.javascript.lcov.reportPaths=coverage/lcov.info
```

### 6.3 Quality Gate

The SonarCloud analysis is executed automatically as part of the CI pipeline.

The **Quality Gate** provides an additional quality validation after the code and automated tests have been processed.

A Pull Request should not be considered fully validated when the required CI or SonarCloud checks fail.

---

## 7. Test Execution Guidelines

### 7.1 Backend

The Docker Compose test environment should be used for Backend integration testing.

The development database must not be used as the integration test database.

The PostgreSQL test database must be available before the Backend tests start.

Django migrations must be applied before executing the tests.

The test environment should be removed after execution:

```bash
docker compose -f deploy/docker-compose.test.yml down -v --remove-orphans
```

### 7.2 Frontend

Dependencies should be installed using:

```bash
npm ci
```

The automated test suite should be executed before considering the change complete:

```bash
npm test
```

Coverage should be generated when validating the CI/SonarCloud process:

```bash
npm run test:coverage
```

The lint and production build should also be validated:

```bash
npm run lint
npm run build
```

### 7.3 Code Review

Test implementation should follow the existing project testing guidelines.

During Code Review, reviewers should verify:

* test names clearly describe the expected behavior;
* relevant edge cases are covered;
* new logic is protected by automated tests;
* the appropriate test layer is used;
* coverage is consistent with the affected code;
* CI checks are successful before the Pull Request is merged.

The project's existing Wiki already defines these Code Review criteria and distinguishes unit tests from tests that exercise endpoints, databases or component behavior.

---

## 8. Validation Criteria

A test-related change is considered validated when:

* all required automated tests pass;
* the required test reports are generated;
* ESLint completes without errors;
* the production build completes successfully when applicable;
* the GitHub Actions workflow completes successfully;
* the SonarCloud analysis completes successfully;
* the required Quality Gate check passes.

---

## 9. A6-24 Validation Results

The A6-24 implementation was validated locally and through GitHub Actions.

### Backend

```text
19 tests
19 passed
0 failures
96% coverage
```

The following items were also validated:

```text
PostgreSQL test container
Django migrations
Docker Compose test environment
coverage.xml
test-results.xml
Environment cleanup
```

### Frontend

```text
6 test files
25 tests
25 passed
0 failures
84.78% statement coverage
```

The following commands were also validated successfully:

```text
npm run lint
npm run build
```

### CI/CD

The implemented GitHub Actions workflows were validated successfully.

The Backend Pull Request completed the CI and SonarCloud checks successfully, including the SonarCloud Quality Gate.

The Frontend Pull Request completed the test, build and SonarCloud workflow successfully, including the SonarCloud Quality Gate.

---

## 10. Maintenance

The test infrastructure should be updated whenever the application's testing strategy or CI/CD process changes.

Changes to the following items should be reflected in this documentation:

```text
Docker Compose test environment
Test commands
Test frameworks
Coverage configuration
GitHub Actions workflows
SonarCloud configuration
Test report locations
```

Generated test reports and coverage artifacts must remain excluded from version control.

This document should be reviewed whenever the project's testing process is changed to ensure that the documented procedure remains consistent with the actual implementation.
