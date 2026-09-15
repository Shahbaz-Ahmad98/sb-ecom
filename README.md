# 🛒 SB-Ecom — E-Commerce Backend

SB-Ecom is a **RESTful E-Commerce backend application** built using **Java and Spring Boot**. The project provides APIs for managing products, categories, users, authentication, and shopping carts.

It is designed as a backend-focused project to demonstrate practical experience with **Spring Boot, REST APIs, Spring Data JPA, Hibernate, database management, authentication, and layered application architecture**.

---

## 🚀 Features

* 🔐 User Authentication & Authorization
* 👤 User Management
* 📦 Product Management
* 🗂️ Category Management
* 🛒 Shopping Cart Management
* 🔄 CRUD REST APIs
* 🗄️ Database Integration using JPA/Hibernate
* ✅ Request Validation
* 📋 DTO-based API responses
* 🔍 Exception Handling
* 🧩 Layered Architecture
* 🧪 API testing using Postman

---

## 🛠️ Tech Stack

| Technology          | Usage                                |
| ------------------- | ------------------------------------ |
| **Java**            | Core programming language            |
| **Spring Boot**     | Backend application framework        |
| **Spring Web**      | REST API development                 |
| **Spring Data JPA** | Database interaction                 |
| **Hibernate**       | ORM                                  |
| **H2 Database**     | Development/testing database         |
| **MySQL**           | Production-style relational database |
| **Maven**           | Dependency management & build        |
| **Lombok**          | Boilerplate code reduction           |
| **ModelMapper**     | DTO ↔ Entity mapping                 |
| **Postman**         | API testing                          |
| **Git & GitHub**    | Version control                      |

---

## 🏗️ Project Architecture

The project follows a **layered architecture** to keep the application organized and maintainable.

```text
Client / Postman
       │
       ▼
┌──────────────────┐
│    Controller    │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│     Service      │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│    Repository    │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│     Database     │
└──────────────────┘
```

### Main Layers

**Controller Layer**

* Handles HTTP requests.
* Defines REST endpoints.
* Sends responses to clients.

**Service Layer**

* Contains business logic.
* Processes application operations.

**Repository Layer**

* Communicates with the database.
* Uses Spring Data JPA repositories.

**Entity Layer**

* Represents database tables using JPA entities.

**DTO Layer**

* Defines the data exposed through APIs.
* Helps separate API models from database entities.

---

## 📁 Project Structure

```text
src
└── main
    ├── java
    │   └── com.ecommerce.project
    │       ├── config
    │       ├── controllers
    │       ├── dto
    │       ├── entities
    │       ├── exceptions
    │       ├── repositories
    │       ├── services
    │       └── SbEcomApplication.java
    │
    └── resources
        ├── application.properties
        └── static/
```

> The exact package structure may change as the project evolves.

---

## 📦 Core Modules

### 1. Category Management

The category module allows the application to organize products into different categories.

Typical operations include:

* Create category
* Get all categories
* Get category by ID
* Update category
* Delete category

---

### 2. Product Management

The product module handles the products available in the store.

Typical operations include:

* Create product
* Get products
* Get product by ID
* Update product
* Delete product
* Associate products with categories

---

### 3. Authentication

The application includes authentication-related functionality for handling users and securing application operations.

The authentication module is designed to provide:

* User registration
* User authentication
* User-related operations
* Authentication utility functionality

---

### 4. Cart Management

The cart module allows users to manage products they intend to purchase.

Cart functionality includes:

* Create/manage carts
* Add products to cart
* Update cart items
* Remove cart items
* Retrieve cart information
* Manage cart quantities

---

## 🗄️ Database

The application uses **JPA/Hibernate** for object-relational mapping.

### Main Entities

```text
User
 │
 └── Cart
      │
      └── CartItem
             │
             └── Product
                    │
                    └── Category
```

The relationships between entities are managed using JPA annotations such as:

```java
@Entity
@OneToMany
@ManyToOne
@OneToOne
```

---

## 🔗 REST API

The application exposes RESTful APIs for interacting with the e-commerce system.

Example endpoint structure:

```text
/api
├── /categories
├── /products
├── /users
├── /auth
└── /carts
```

### Example Requests

#### Get Categories

```http
GET /api/categories
```

#### Get Products

```http
GET /api/products
```

#### Create Product

```http
POST /api/products
```

#### Get Cart

```http
GET /api/carts/{cartId}
```

> Endpoint paths may change as the project continues to evolve.

---

## ⚙️ Getting Started

### Prerequisites

Make sure you have the following installed:

* Java JDK
* Maven
* Git
* IntelliJ IDEA or another Java IDE
* Postman (recommended)

---

## 📥 Clone the Repository

```bash
git clone https://github.com/Shahbaz-Ahmad98/sb-ecom.git
```

Navigate to the project:

```bash
cd sb-ecom
```

---

## ▶️ Run the Application

Using Maven:

```bash
mvn spring-boot:run
```

Or run the main class from your IDE:

```text
SbEcomApplication.java
```

The application runs on:

```text
http://localhost:8080
```

---

## 🔧 Configuration

Application configuration is maintained in:

```text
src/main/resources/application.properties
```

Example development configuration:

```properties
spring.application.name=sb-ecom
server.port=8080

spring.datasource.url=jdbc:h2:mem:test
spring.datasource.driverClassName=org.h2.Driver

spring.jpa.hibernate.ddl-auto=create
spring.jpa.show-sql=true
```

> Database configuration should be adjusted according to your local environment.

---

## 🧪 API Testing

The APIs can be tested using **Postman**.

Example workflow:

```text
1. Start Spring Boot application
          ↓
2. Open Postman
          ↓
3. Send API request
          ↓
4. Controller receives request
          ↓
5. Service processes business logic
          ↓
6. Repository communicates with database
          ↓
7. API returns JSON response
```

---

## 📌 Current Development Status

### Completed

* [x] Spring Boot project setup
* [x] Product management
* [x] Category management
* [x] JPA/Hibernate integration
* [x] REST APIs
* [x] Authentication-related functionality
* [x] Cart functionality
* [x] DTO implementation
* [x] Repository & service layers
* [x] API testing with Postman

### Planned Improvements

* [ ] Order management
* [ ] Payment integration
* [ ] Product search and filtering
* [ ] Pagination and sorting
* [ ] Advanced authorization/role management
* [ ] API documentation using Swagger/OpenAPI
* [ ] Unit and integration testing
* [ ] Docker containerization
* [ ] Deployment to a cloud platform
* [ ] Frontend integration

---

## 🔮 Future Scope

The project can be extended into a complete full-stack e-commerce platform by adding:

* React/Angular frontend
* Online payment gateway
* Order tracking
* Wishlist
* Product reviews and ratings
* Email notifications
* Admin dashboard
* Inventory management
* Cloud deployment
* Docker & CI/CD

---

## 🎯 Learning Objectives

This project was developed to gain practical experience with:

* Java backend development
* Spring Boot
* REST API design
* Spring Data JPA
* Hibernate ORM
* Relational database design
* Entity relationships
* DTOs
* Dependency Injection
* Layered architecture
* Authentication
* Git & GitHub
* API testing

---

## 👨‍💻 Author

**Shahbaz Ahmad**

Java Backend Developer

### Technologies & Interests

```text
Java
Spring Boot
Spring Data JPA
Hibernate
REST APIs
MySQL
Git & GitHub
Backend Development
```

---

## ⭐ Support

If you find this project useful for learning or reference, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project is intended primarily for **learning and educational purposes**.
