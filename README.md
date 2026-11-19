# Library Loan System

A REST API for managing a library's book catalog and loans, with role-based
access for librarians (`ADMIN`) and members (`MEMBER`).

## Tech stack

- Java 21, Spring Boot 4.1
- PostgreSQL 17, Spring Data JPA, Flyway
- Spring Security (JWT)
- JUnit 5, Testcontainers
- GitHub Actions
- React + TypeScript (frontend, coming soon)

## Project structure

```
backend/        Spring Boot application
frontend/       React application (coming soon)
compose.yaml    Local infrastructure (PostgreSQL)
```

## Getting started

Prerequisites: JDK 21+, Podman (or Docker) and podman-compose.

```bash
cp .env.example .env          # then change the password in .env
podman-compose up -d          # start PostgreSQL
cd backend
./mvnw spring-boot:run -Dspring-boot.run.profiles=dev
```

Health check: http://localhost:8080/actuator/health

## Running tests

Testcontainers starts its own database, so Compose is not required.

```bash
cd backend
./mvnw verify
```