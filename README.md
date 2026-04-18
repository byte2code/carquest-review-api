# CarQuest Review Service API

Spring Boot REST API for managing car reviews with MySQL persistence and a JWT-enabled security filter setup.

## Overview

This project is a companion microservice for CarQuest. It stores and manages review records for cars and exposes CRUD-style endpoints under `/review`. It is designed to run alongside CarQuest (typically on port `8081`) so the car service can retrieve or submit reviews.

## Concepts and Features Covered

- Spring Boot REST API setup
- Spring Data JPA repository pattern
- MySQL-backed persistence
- CRUD-style endpoints for review records
- JWT authentication filter wiring (bearer-token parsing via `OncePerRequestFilter`)

## Tech Stack

- Java 17
- Spring Boot 2.7
- Spring Web
- Spring Data JPA
- Spring Security
- MySQL
- Maven
- Lombok
- JJWT

## Project Structure

```text
Review/
├── CHANGELOG.md
├── README.md
├── pom.xml
├── mvnw
├── mvnw.cmd
└── src/
    ├── main/
    │   ├── java/com/CN/Review/
    │   │   ├── config/
    │   │   ├── controller/
    │   │   ├── dto/
    │   │   ├── jwt/
    │   │   ├── model/
    │   │   ├── repository/
    │   │   ├── service/
    │   │   └── ReviewApplication.java
    │   └── resources/
    │       └── application.yml
    └── test/
        └── java/
```

## How to Run

1. Open a terminal in the project root.
2. Update MySQL connection values in `src/main/resources/application.yml` if needed.
3. Run `./mvnw test` (fallback: `mvn test`).
4. Run `./mvnw spring-boot:run`.
5. Use the API under `http://localhost:8081/review`.

Available endpoints:

- `POST /review/add`
- `PUT /review/update/{id}`
- `GET /review/{name}`
- `GET /review/getAll`
- `DELETE /review/{id}`

Example request body:

```json
{
  "name": "i20",
  "review": "Smooth ride and good mileage."
}
```

## Notes

- Security config references `/user/register` and `/auth/login`; those endpoints are not present in this template bundle.
- The API endpoints above are implemented under `ReviewController`.

## GitHub Metadata

- Suggested repository description: `Spring Boot REST API for managing car reviews with MySQL persistence and CRUD endpoints (CarQuest companion service).`
- Suggested topics: `java`, `java-17`, `spring-boot`, `spring-security`, `spring-data-jpa`, `mysql`, `rest-api`, `review-service`, `carquest`, `microservices`, `maven`, `learning-project`, `portfolio-project`

