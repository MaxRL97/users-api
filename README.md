# Users API

REST API built with Spring Boot for managing users.

This project was developed as part of a technical assessment and implements a REST service with CRUD operations, filtering, validation, password encryption, and API documentation.

This repository contains the **final and stable version of the API**, ready for testing and evaluation.

---

# Technologies

* Java 17
* Spring Boot 3
* Maven
* Swagger / OpenAPI
* Docker
* JUnit
* Lombok

---

# Features

* CRUD operations for users
* User filtering
* Field validations
* Password encryption
* UUID generation
* Timestamp creation
* Nested address objects
* Swagger API documentation
* Unit tests
* Docker support

---

# Project Structure

```
src
 ├ main
 │  ├ java
 │  │  └ com.example.users_api
 │  │      ├ controller
 │  │      ├ service
 │  │      ├ model
 │  │      └ util
 │  └ resources
 │      └ application.properties
 │
 └ test
     └ java
         └ com.example.users_api
             └ service
```

---

# Initial Data

The API initializes with **3 predefined users stored in memory**, each containing:

* UUID identifier
* Email
* Name
* Phone
* Encrypted password
* Tax ID
* Creation timestamp
* List of addresses

Each user includes two addresses:

* Work address
* Home address

---

# Running the Project

## Option 1 — Run with Maven Wrapper

From the project root:

```
./mvnw spring-boot:run
```

Windows:

```
mvnw.cmd spring-boot:run
```

The API will start on:

```
http://localhost:8080
```

---

# Swagger Documentation

Swagger UI is available at:

```
http://localhost:8080/swagger-ui/index.html
```

Swagger allows you to:

* Explore available endpoints
* Send requests directly from the browser
* View request and response models

---

# API Endpoints

## Get All Users

```
GET /users
```

Optional filter parameter:

```
GET /users?filter=user1
```

---

## Create User

```
POST /users
```

Example request body:

```json
{
  "email": "newuser@mail.com",
  "name": "newuser",
  "phone": "+1 55 555 555 99",
  "password": "password123",
  "taxId": "TEST990101XXX",
  "addresses": [
    {
      "id": 1,
      "name": "home",
      "street": "Main Street",
      "countryCode": "US"
    }
  ]
}
```

---

## Update User

```
PATCH /users/{id}
```

---

## Delete User

```
DELETE /users/{id}
```

---

# Validation Rules

The API includes validations for:

* Email format
* Required fields
* Password presence
* Address structure

---

# Postman Collection

A Postman collection is included in this repository:

```
Users_API.postman_collection.json
```

To use it:

1. Open Postman
2. Click **Import**
3. Select the JSON file
4. Run the requests

---

# Running Tests

To run the unit tests:

```
./mvnw test
```

or on Windows:

```
mvnw.cmd test
```

---

# Docker

This project includes a Dockerfile to run the API inside a container.

## Build the Docker Image

```
docker build -t users-api .
```

## Run the Container

```
docker run -p 8080:8080 users-api
```

The API will be available at:

```
http://localhost:8080
```

---

# Author

Maximiliano Ramirez
