# Task Manager REST API (Spring Boot, JPA & Hibernate)

A RESTful Task Manager API built with Spring Boot and Spring Data JPA, with full database persistence. It supports creating, reading, updating, and deleting tasks, with paginated results and validated input.

Built as part of a structured Java developer internship at 4impact Philippines.

## What this project demonstrates

- REST API design with proper HTTP methods and status codes (`ResponseEntity`)
- Layered architecture: Controller → Service → Repository
- Spring Data JPA and Hibernate with a relational database
- Custom JPQL queries and pagination
- DTOs to separate API models from database entities
- Centralized error handling with `@ControllerAdvice`
- API testing with Postman

## Tech stack

| Area | Technology |
|------|------------|
| Language | Java 21 |
| Framework | Spring Boot |
| Persistence | Spring Data JPA, Hibernate |
| Database | Microsoft SQL Server |
| Build tool | Maven |
| Testing | Postman |

## Project structure

```
src/main/java/.../
├── controller/   # REST endpoints
├── service/      # Business logic
├── repository/   # Spring Data JPA repositories
├── model/        # JPA entities
├── dto/          # Request/response objects
└── exception/    # Custom exceptions and global handler
```


## API endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/tasks` | Get all tasks (supports pagination) |
| GET | `/api/tasks/{id}` | Get a task by ID |
| POST | `/api/tasks` | Create a new task |
| PUT | `/api/tasks/{id}` | Update a task |
| DELETE | `/api/tasks/{id}` | Delete a task |


### Example request

`POST /api/tasks`

```json
{
  "title": "Finish README",
  "description": "Document the Task Manager API",
  "completed": false
}
```

### Example response

```json
{
  "id": 1,
  "title": "Finish README",
  "description": "Document the Task Manager API",
  "completed": false
}
```


## Getting started

### Prerequisites

- JDK 21
- Maven
- SQL Server (or the database you use) running locally

### Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/Strawvani/Task-Manager-API-JPA.git
   cd Task-Manager-API-JPA
   ```

2. Create a database, then set your connection details in `src/main/resources/application.properties`:

   ```properties
   spring.datasource.url=jdbc:sqlserver://localhost:1433;databaseName=taskdb;encrypt=true;trustServerCertificate=true
   spring.datasource.username=YOUR_USERNAME
   spring.datasource.password=YOUR_PASSWORD
   spring.jpa.hibernate.ddl-auto=update
   ```

3. Run the application:

   ```bash
   ./mvnw spring-boot:run
   ```

   [Use `./gradlew bootRun` if you use Gradle.]

4. The API will be available at `http://localhost:8080`.

## What I learned

- Fixing N+1 query problems with `JOIN FETCH`
- Handling SQL Server-specific issues (reserved keywords and column definitions)
- Why DTOs and a service layer keep controllers simple and the code easier to maintain

## Roadmap

- [ ] Unit tests with JUnit and Mockito
- [ ] Swagger/OpenAPI documentation
- [ ] Dockerfile and Docker Compose
- [ ] GitHub Actions build workflow
- [ ] Authentication with Spring Security and JWT

## Author

Jordan M. Gonzales
GitHub: [@Strawvani](https://github.com/Strawvani)
LinkedIn: [jordan-gonzales-bb3ba1346](https://linkedin.com/in/jordan-gonzales-bb3ba1346)
