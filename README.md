# Job Portal API

A simple Spring Boot REST API for browsing and searching job listings, developed during the **IBM Java Developer** course.

## 🎯 Purpose

Demonstrates the basics of building a REST API with Spring Boot:

- Bootstrapping with `@SpringBootApplication`
- Exposing REST endpoints with `@RestController`
- Handling path variables with `@PathVariable`
- Initializing in-memory data with `@PostConstruct`
- Tracking views and last access time on job listings

## 🛠️ Tech Stack

- Java 21
- Spring Boot 4.1.1
- Maven
- Spring Boot Starter Web MVC

## 🌐 Endpoints

| Method | Path                     | Description                                                            |
| ------ | ----------------------- | ---------------------------------------------------------------------- |
| `GET`  | `/jobs`                 | Returns all job listings, updates `lastAccessDate` and increments `numViews` |
| `GET`  | `/jobs/search/{query}` | Returns jobs whose title or description contains the query (case-insensitive) |


### Example requests

curl <http://localhost:8080/jobs>
curl <http://localhost:8080/jobs/search/engineer>
curl <http://localhost:8080/jobs/search/data>

Example response
json
[
  {
    "id": "1",
    "title": "Software Engineer",
    "description": "Develop software applications",
    "postingDate": "2026-10-10",
    "lastAccessDate": "2026-10-10T20:30:00"
  }
]

▶️ How to Run

mvn spring-boot:run

The application starts an embedded Tomcat server on port 8080.

📦 Build

mvn clean package

Run the generated JAR:

java -jar target/jobportal-0.0.1-SNAPSHOT.jar

📌 Notes

- No database is used — jobs are stored in memory
- Two sample jobs are loaded at startup via @PostConstruct
- Data is reset on every application restart

👤 Author

Hardy Fernandes

Developed as part of the IBM Java Developer course.
