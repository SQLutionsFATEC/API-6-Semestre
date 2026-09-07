# IAzimute

![sqlutions logo](https://github.com/user-attachments/assets/4884e8b3-b59a-45ba-ad13-13faa8d4d9b3)

### Welcome to the repository of project IAzimute, developed by team **_SQLutions_** for the 6th Semester Database course at FATEC São José dos Campos.

---

<div align="center">

[The Challenge](#-the-challenge) | [Backlogs and User Stories](#-backlogs--user-stories) | [Technologies](#%EF%B8%8F-technologies) | [Team](#-team)

</div>


## 📑 The Challenge

---

The client reported that the engineers have a hard time finding and classifying documents, this process is manual and takes a extremely long time, the consequence is a loss and stop of the current task to read hundreds of pages from documents hoping the document contains information from the task, this takes minutes to hours of time, the other problem is classifying these documents with "tags" to make finding them easier, the process is also manual and takes minutes to hours at a time. 

## The Solution (IAzimute)

---

We decided to build a web application to and organize, classify and turn the search for documents easy for any employee.
Our project offers:
- A search bar to find documents based on name or even context from the documents.
- Filters to hasten the search. 


### 🏁 Sprint Deliverables

|Sprint|Forecast|Status|History|
|---|---|---|---|
|01|09/07/2026 to 09/27/2026|Current Stage|On going|
|02|10/05/2026 to 10/25/2026|Future Stage|Future Stage|
|03|11/02/2026 to 11/22/2026|Future Stage|Future Stage|

[→ Back to top](#IAzimute)

## 🎯 Backlogs & User Stories

### ✅ Functional Requirements

| ID    | Functionality                     | Description                                                                                                                                       | Priority |
| ----- | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| RF-1  | Search by Document Name     | Allow users to quickly search for files by partial or full name.                                                        | High     |
| RF-2  | Automatic Classification            | The system must automatically associate labels to each document to facilitate the search process.                                                                                                  | High     |
| RF-3  | Internal Text Search Engine        | Index and allow the search of specific technical terms directly within the internal content of the files (e.g., PDFs).                                                                                     | High     |
| RF-4  | Technical Standards Filter                 | Allow filtering the search by crossing labels and technical standards associated with documents of similar content.                                          | High   |
| RF-5  | Audit System (Logs)                    | TImplement access and data manipulation logs for traceability.                                                                         | Medium     |
| RF-6  | Access Control and Permissions            | Restrict file viewing and manipulation only to users with the proper security clearances.                          | High     |
| RF-7  | LGPD Compliance | Implement data anonymization and database de-characterization records, ensuring the right to be forgotten.                                                        | High     |
| RF-8  | Access Request Flow              | Create a process in the system so that engineers can formally request access to restricted documents, avoiding physical requests.                         | Low     |


---

### ⚙️ Non-Functional Requirements

| ID    | Category                     | Description                                                                                                                                       | 
| ----- | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| RNF-1  | Artificial Intelligence    | The system must use some form of Machine Learning to solve the problem.                                                        |
| RNF-2  | Documentation            | The project must contain the API (Application Programming Interface) Documentation.    |
| RNF-3  | Modeling        | Delivery of the Database or Data File Modeling is mandatory..                                                                                     |
| RNF-4  | Security / LGPD                 | The system must have data anonymization implemented according to LGPD guidelines.                        |
| RNF-5  | Audit System (Logs)                    | The system must continuously record access and data manipulation logs.                                    |
| RNF-6  | Security / LGPD            | The system must maintain records of database de-characterization.                         |


---

### 📌 Product Backlog

---



|Rank|Priority|User Story|Estimate|Sprint|Functional Requisite|Non-Functional Requisites|
|---|---|---|---|---|---|---|
|1|High|[[US-01]] - As an employee, I want to search for documents by name, so that I can quickly find the exact file I need, saving time locating documents.|5|1|RF-1| RNF-2, RNF-3|
|2|High|[[US-02]] - As an operator, I want documents to be automatically classified using tags to facilitate the use of the system by engineers, saving search time and improving document organization in the system.|13|1|RF-2|RNF-1|
|3|High|[[US-03]] - As an engineer, I want the search to include the internal text of the documents, to locate specific technical information even when I don't know the file title, saving the time of reading all files.|13|2|RF-3|RNF-1, RNF-2|
|4|High|[[US-04]] - As an engineer, I want the search to use the standards/tags attached to the documents, to ensure I am consulting the correct regulatory documentation, thus saving time manually identifying what each file is about.|5|2|RF-3|RNF-2|
|5|High|[[US-06]] - As an operator, I want users to only have access to files they are cleared for, so that document information remains secure and prevents costs from data leaks.|8|2|RF-6|RNF-5|
|6|High|[[US-07]] - As an employee, I want to exercise my data protection rights, to preserve my privacy and the right to be forgotten.|8|2|RF-7|RNF-4, RNF-6|
|7|Medium|[[US-05]] - As an operator, I want access to an auditing system, to track accesses to the system's documents.|5|3|RF-5|RNF-5|
|8|Low|[[US-08]] - As an engineer, I want to be able to request access to documents to obtain necessary information, saving time in the process of going in person to request document access.|5|3|RF-8|RNF-2|

### 📌 Sprint Backlog

---

### [1️⃣ Sprint 1 - Backlog](/docs/project/Sprints/Sprint%201/Sprint_1.md)



### [Youtube video]

---

### [2️⃣ Sprint 2 - Backlog](/docs/project/Sprints/Sprint%202/Sprint_2.md)



### [Youtube video]

---

### [3️⃣ Sprint 3 - Backlog](/docs/project/Sprints/Sprint%203/Sprint_3.md)



### [Youtube video]

[→ Back to top]((#IAzimute))

## 🛠️ Technologies

The following tools, languages, libraries, and technologies were used in the project's construction:

[![Jira](https://img.shields.io/badge/jira-%230A0FFF.svg?style=for-the-badge&logo=jira&logoColor=white)](https://www.atlassian.com/software/jira)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/seu-usuario) 
[![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)](https://git-scm.com/)
[![Figma](https://img.shields.io/badge/Figma-0ACF83?style=for-the-badge&logo=figma&logoColor=white)](https://www.figma.com/) 
[![Prettier](https://img.shields.io/badge/prettier-%23F7B93E.svg?style=for-the-badge&logo=prettier&logoColor=black)](https://prettier.io/)
[![ESLint](https://img.shields.io/badge/ESLint-4B32C3?style=for-the-badge&logo=eslint&logoColor=white)](https://github.com/eslint/eslint)
[![SonarQube](https://img.shields.io/badge/SonarQube-black?style=for-the-badge&logo=sonarqube&logoColor=4E9BCD)](https://www.sonarsource.com/products/sonarqube/)

### Backend
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
[![Pytest](https://img.shields.io/badge/pytest-%23ffffff.svg?style=for-the-badge&logo=pytest&logoColor=2f9fe3)](https://docs.pytest.org)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/) 


### Frontend
![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)


[→ Back to top]((#synthesi))

## 👥 Team

| Photo                                                                                                   | Function      | Name                         | Socials                                                                                                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------- | ------------- | ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![bryan](https://github.com/user-attachments/assets/de3c76c1-183c-4e13-8856-7dd87834be2b)               | Product Owner | Bryan Matheus                | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bryan-matheus-5aa0a3302)         [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/BryanARMatheus)      |
| ![gabriel vasconcelos](https://github.com/user-attachments/assets/0ac1090d-15b5-44a9-b68c-79e890a1783d) | Scrum Master     | Gabriel Vasconcelos Ferreira | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/gabriel-vasconcelos-255979262)<br>[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/gabrielvascf)       |
| ![caina](https://github.com/user-attachments/assets/a6f52b8c-11c7-4f20-9647-004cd04c60bc)               | Developer     | Cainã Nascimento Melo        | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/cain%C3%A3-melo/)                [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CainaNascimentoMelo) |
| ![daniel](https://github.com/user-attachments/assets/6cb4f0c1-0bef-43ff-8e57-e633f145dbdf)              | Developer  | Daniel Sendreti Broder       | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/danielbroder)                    [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/d-broder)            |
| ![enzo](https://github.com/user-attachments/assets/f228df2a-1bae-408d-9d39-d5808bea56bc)                | Developer     | Enzo Lemos Franco            | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/enzo-lemos-franco-002651293/)  <br>[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/EnzoLFranco)       |
| ![elbert](https://github.com/user-attachments/assets/a8f976c3-c1cb-4297-bdda-15ea4da1d94b)   | Developer     | Elbert Jean       | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/elbertjean)      [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ElbertJean)      |
| ![gabriel carvalho](https://github.com/user-attachments/assets/20a93e32-fdf9-4bbe-b798-08a1985c5db6)    | Developer     | Gabriel Carvalho Silva       | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/gabriel-carvalho-87569336a)      [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Gabriecarvalho)      |
| ![gloria](https://github.com/user-attachments/assets/2de16de0-fd28-4700-b5b5-a00702dfce10)              | Developer     | Glória Brito                 | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/gloriafbrito/)                   [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/GloBrito)            |

[→ Back to top](#synthesi)
