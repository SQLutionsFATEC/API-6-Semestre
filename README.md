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
We decided to build a web application to organize, classify, and simplify the search for technical and regulatory prioritizing a frictionless user experience and high-standard data security.

Our project offers:
* **Smart Search by Name and Context:** Quickly find files not only by title, but also through full internal content indexing and automated tag classification to assist your search.
* **Advanced & Regulatory Filters:** Accelerate searches by cross-referencing metadata such as standard types, sectors, and specific tags to ensure access to the correct regulatory documentation.
* **Secure In-Browser Viewer:** Open documents directly within the system in a protected environment to discourage leaks and unauthorized downloads.
* **Centralized Upload Management:** Allow operators/admins to upload new PDF files directly through the web interface with mandatory metadata, automatically classifying these documents upon insertion to instantly centralize the knowledge base.
* **Agile Metadata & Tag Editing:** Enable operators to conveniently fix file indexing errors and update regulatory classifications.
* **Access Control by Level and Sector:** Granular security integrated with Keycloak, ensuring automatic access exclusively for authorized employees.
* **LGPD Compliance:** Full support for data privacy, featuring editable profiles, audit logs for traceability, and the right to be forgotten through database record anonymization.

### 🏁 Sprint Deliverables

|Sprint|Forecast|Status|History|
|---|---|---|---|
|01|09/07/2026 to 09/27/2026|Completed Stage|Complete|
|02|10/05/2026 to 10/25/2026|Completed Stage|Complete|
|03|11/02/2026 to 11/22/2026|Current Stage|On going|

[→ Back to top](#IAzimute)

## 🎯 Backlogs & User Stories

### ✅ Functional Requirements

| ID | Functionality | Description | Priority |
| --- | --- | --- | --- |
| RF-1 | Search by Document Name | Allow users to quickly search for files by partial or full name. | High |
| RF-2 | Automatic Classification | The system must automatically associate labels to each document to facilitate the search process. | High |
| RF-3 | Internal Text Search Engine | Index and allow the search of specific technical terms directly within the internal content of the files (e.g., PDFs). | High |
| RF-4 | Technical Standards Filter | Allow filtering the search by crossing labels and technical standards associated with documents of similar content. | High |
| RF-5 | Conversational AI Assistant (RAG) | Provide an internal conversational AI chatbot utilizing local RAG architecture to help users find documents based on contextual descriptions rather than exact titles or contents. | High |
| RF-6 | Access Control and Permissions | Restrict file viewing and manipulation only to users with the proper security clearances. | High |
| RF-7 | LGPD Compliance | Implement data anonymization, database de-characterization records, consent management, and the right to be forgotten. | High |
| RF-8 | Access Request Workflow | Enable engineers to formally request access to restricted documents and allow operators to review, approve, or deny these requests via a dedicated management interface. | Medium |
| RF-9 | Document Upload | Allow operators to upload physical document files (e.g., PDF) directly through the website interface with mandatory metadata. | High |
| RF-10 | Secure In-Browser Viewer | Enable users to view documents directly inside the system via a secure browser stream, incorporating dynamic watermarking and copy/print deterrents. | High |
| RF-11 | Metadata & Tag Management | Allow operators to update document metadata (name, type, sector, access level) and tags in a single unified interface. | High |
| RF-12 | LGPD Consent & Transparency Management | Allow users to review, agree, or decline consent regarding personal data processing, and receive automated notifications regarding security posture or data incidents. | High |
| RF-13 | Administrative User Management Dashboard | Provide operators with a dedicated dashboard to view, control, and manage system users, roles, sectors, and access permissions. | Medium |

---

### ⚙️ Non-Functional Requirements

| ID | Category | Description |
| :--- | :--- | :--- |
| RNF-1 | Artificial Intelligence | The system must use local Machine Learning models (Ollama/Llama 3.1 & local Cross-Encoder Reranker) for semantic search and conversational RAG. |
| RNF-2 | Documentation | The project must contain complete API (Application Programming Interface) Documentation. |
| RNF-3 | Modeling | Delivery of the Database or Data File Modeling is mandatory. |
| RNF-4 | Security / LGPD | The system must have data anonymization, consent logging, and security alerting implemented according to LGPD guidelines. |
| RNF-5 | Audit & Traceability | The system must continuously record access, permissions changes, and data manipulation logs for traceability. |
| RNF-6 | Security / LGPD | The system must maintain records of database de-characterization and secure data retention/deletion. |

---

### 📌 Product Backlog

| Rank | Priority | User Story | Estimate | Sprint | Functional Requisite | Non-Functional Requisites |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | High | **[US-01]** - As an employee, I want to search for documents by name, so that I can quickly find the exact file I need, saving time locating documents. | 5 | 1 | RF-1 | RNF-2, RNF-3 |
| 2 | High | **[US-02]** - As an operator, I want documents to be automatically classified using tags to facilitate the use of the system by engineers, saving search time and improving document organization. | 13 | 1 | RF-2 | RNF-1 |
| 3 | High | **[US-03]** - As an engineer, I want the search to include the internal text of the documents, to locate specific technical information even when I don't know the file title. | 13 | 1 | RF-3 | RNF-1, RNF-2 |
| 4 | High | **[US-04]** - As an engineer, I want the search to use standards/tags attached to documents, ensuring I consult correct regulatory documentation and saving identification time. | 5 | 2 | RF-4 | RNF-2 |
| 5 | High | **[US-10]** - As a user, I want to view documents directly in the system via an in-browser secure viewer with dynamic watermarking, to access information quickly without local downloads. | 5 | 2 | RF-10 | RNF-5, RNF-6 |
| 6 | High | **[US-11]** - As an operator, I want to upload documents directly via the website interface, to centralize the knowledge base agilely and ensure instant availability. | 3 | 2 | RF-9 | RNF-3 |
| 7 | Medium | **[US-09]** - As an operator, I want to modify document metadata (name, type, sector, access level) and tags in a single modal, to correct indexing errors and keep categorization accurate. | 3 | 2 | RF-11 | RNF-3 |
| 8 | Medium | **[US-06]** - As an operator, I want users to only have access to files they are cleared for (based on sector and access level), so that document information remains secure. | 8 | 2 | RF-6 | RNF-5 |
| 9 | Medium | **[US-07]** - As a user, I want to exercise my data protection rights (profile editing and right to be forgotten via account deletion with anonymization), to preserve my privacy. | 5 | 2 | RF-7 | RNF-4, RNF-6 |
| 10 | Medium | **[US-12]** - As a user, I want to review and manage my consent preferences regarding personal data processing, ensuring full compliance and transparency under LGPD. | 3 | 3 | RF-12 | RNF-4 |
| 11 | Medium | **[US-13]** - As a user, I want to be notified of security alerts or data protection procedures in case of incidents, ensuring transparency and compliance with LGPD requirements. | 3 | 3 | RF-12 | RNF-4 |
| 12 | Medium | **[US-14]** - As an engineer or operator, I want document tags/labels to encompass keywords and technical standards, optimizing both manual filters and conversational search. | 5 | 3 | RF-2, RF-4 | RNF-1 |
| 13 | Medium | **[US-08]** - As an engineer, I want to formally request access to restricted documents, and as an operator, I want a management page to review and approve/deny requests, replacing in-person processes. | 5 | 3 | RF-8 | RNF-2, RNF-5 |
| 14 | Medium | **[US-15]** - As an operator, I want a dedicated administrative dashboard to view and control system users, roles, and access permissions, ensuring secure account governance. | 8 | 3 | RF-13 | RNF-5 |
| 15 | Medium | **[US-05]** - As an engineer, I want an AI chatbot to help me find documents when I know the context but not the exact title or content, saving time during technical research. | 13 | 3 | RF-5 | RNF-1, RNF-5 |

### 📌 Sprint Backlog

---

### [1️⃣ Sprint 1 - Backlog](/docs/project/Sprints/Sprint%201/Sprint_1.md)

https://github.com/user-attachments/assets/abbcb71d-7773-4b2e-941a-0e8c8788fd75

### [Youtube video](https://www.youtube.com/watch?v=T49qXj-Kcdc)

---

### [2️⃣ Sprint 2 - Backlog](/docs/project/Sprints/Sprint%202/Sprint_2.md)


## Sprint review
https://github.com/user-attachments/assets/4257af22-6df1-49d7-84c3-97e92e672575


### [Youtube video](https://youtu.be/ulyPjKx72JM)

---

## Application Running
https://github.com/user-attachments/assets/397d30c3-280a-4758-90a8-94ebc73689e4

### [Youtube video](https://www.youtube.com/watch?v=iJTb0-J2CRk)



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
