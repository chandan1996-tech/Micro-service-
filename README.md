# Micro-service-
# Microservices Architecture & API Communication

## REST Client using RestTemplate and WebClient

This project demonstrates **Microservices Architecture**, **REST API communication**, and **service-to-service communication** using Spring Boot.

The project contains two independent microservices:

- **Course Service** – Provides course information through REST APIs.
- **Student Service** – Provides student information and communicates with Course Service using a REST Client.

The project demonstrates communication using:

- `RestTemplate`
- `WebClient`
- REST APIs
- HTTP methods
- JSON
- Service-to-service communication

---

# 1. What is Microservices Architecture?

Microservices Architecture is a software architecture where a large application is divided into multiple small, independent services.

Each service:

- Performs a specific business function
- Can be developed independently
- Can be deployed independently
- Can have its own database
- Communicates with other services through APIs

### Example

```text
                 Client / Postman
                       |
                       v
                Student Service
                  Port: 8081
                       |
                       | REST API
                       v
                 Course Service
                  Port: 8082
```

---

# 2. Project Architecture

```text
microservices-rest-client
│
├── student-service
│   ├── src
│   ├── pom.xml
│   └── README.md
│
└── course-service
    ├── src
    ├── pom.xml
    └── README.md
```

---

# 3. Services

## Course Service

Course Service is responsible for providing course information.

### Port

```text
8082
```

### Base URL

```text
http://localhost:8082
```

### Example API

```http
GET http://localhost:8082/courses/1
```

### Response

```json
{
    "id": 1,
    "name": "Java Full Stack",
    "duration": 60
}
```

---

# 4. Student Service

Student Service is responsible for student-related operations.

### Port

```text
8081
```

### Base URL

```text
http://localhost:8081
```

Student Service also communicates with Course Service.

```text
Student