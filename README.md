![Java](https://img.shields.io/badge/Java-11-orange?logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-2.7-brightgreen?logo=springboot)
![Maven](https://img.shields.io/badge/Maven-Build-red?logo=apachemaven)
![Docker](https://img.shields.io/badge/Docker-Ready-blue?logo=docker)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

# Task Manager API

A **Spring Boot-based RESTful Task Management System** that enables users to securely manage tasks — create, update, delete, and track progress — with JWT-based authentication, database persistence, and container-ready architecture.

---

## Features

**User Authentication & Authorization**
- Secure login/register using Spring Security + JWT  
- Role-based access control for users  

**Task Management APIs**  
- Create, update, delete, and list tasks  
- Each user can manage their own tasks independently  

**Persistence & ORM**  
- Data persisted via **Spring Data JPA (Hibernate)**  
- Currently runs on **H2 in-memory database** (can easily switch to MySQL)  

**Container-Ready**  
- Includes `Dockerfile` and `docker-compose.yml` for one-command deployment  
- Stateless architecture for cloud scalability  

**Developer Tools**  
- Live H2 console for debugging  
- In-memory database auto-schema creation  
- Easily extensible for PostgreSQL or MySQL  

---

## Tech Stack

| Layer | Technology |
|:------|:------------|
| Backend | Spring Boot 2.7.x |
| Security | Spring Security, JWT |
| Database | H2 (In-Memory) / MySQL (switchable) |
| ORM | Hibernate / JPA |
| Build Tool | Maven |
| Containerization | Docker |
| Language | Java 11 |
| Testing | JUnit (Spring Boot Starter Test) |

---

## Architecture Overview

```text
                        ┌──────────────────────────────┐
                        │        REST Controller        │
                        │ (Handles API requests & maps) │
                        └──────────────┬────────────────┘
                                       │
                                       ▼
                        ┌──────────────────────────────┐
                        │          Service Layer        │
                        │  (Business logic, validation) │
                        └──────────────┬────────────────┘
                                       │
                                       ▼
                        ┌──────────────────────────────┐
                        │        Repository Layer       │
                        │ (CRUD operations via JPA/HQL) │
                        └──────────────┬────────────────┘
                                       │
                                       ▼
                        ┌──────────────────────────────┐
                        │     H2 / MySQL Database       │
                        │ (Data persistence & relations)│
                        └──────────────────────────────┘
                                       ▲
                                       │
                        ┌──────────────────────────────┐
                        │  JWT Auth + Spring Security   │
                        │ (Access control, token verify)│
                        └──────────────────────────────┘
