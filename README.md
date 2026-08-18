# 🛒 SB E-Commerce Backend

A backend REST API for an E-Commerce application built using **Java, Spring Boot, Spring Data JPA, Hibernate, and H2 Database**.

The project follows a layered architecture to provide a clean separation between controllers, business logic, repositories, entities, DTOs, and database operations.

---

## 📌 Project Overview

**SB E-Commerce** is a Java Spring Boot backend application designed to manage the core functionality of an online shopping platform.

The current implementation focuses on:

* Product management
* Category management
* Product-category relationships
* File/image handling
* RESTful APIs
* DTO-based request/response handling
* Database persistence using JPA/Hibernate
* Validation
* Exception handling

The project is designed with scalability and maintainability in mind and can be extended with authentication, shopping cart, orders, payments, and other e-commerce features.

---

## 🚀 Features

### Product Management

* Create products
* Retrieve products
* Update products
* Delete products
* Manage product information
* Associate products with categories

### Category Management

* Create categories
* Retrieve categories
* Update categories
* Delete categories
* Manage product categories

### File Handling

* Upload product-related files/images
* Separate file handling service

### Backend Features

* RESTful API architecture
* Layered architecture
* DTO and Entity separation
* ModelMapper integration
* Spring Data JPA
* Hibernate ORM
* Request validation
* Exception handling
* H2 database integration

---

## 🛠️ Tech Stack

| Technology              | Purpose                       |
| ----------------------- | ----------------------------- |
| **Java 25**             | Backend programming           |
| **Spring Boot 4.1.0**   | Application framework         |
| **Spring MVC**          | REST API development          |
| **Spring Data JPA**     | Database operations           |
| **Hibernate**           | ORM                           |
| **H2 Database**         | Development database          |
| **Maven**               | Build & dependency management |
| **Lombok**              | Reduce boilerplate code       |
| **ModelMapper**         | DTO ↔ Entity mapping          |
| **Hibernate Validator** | Request validation            |

---

## 🏗️ Project Architecture

The application follows a **Layered Architecture**:

```text
                    Client / Postman
                           │
                           ▼
                ┌────────────────────┐
                │    Controller      │
                │                    │
                │ ProductController  │
                │ CategoryController │
                └─────────┬──────────┘
                          │
                          ▼
                ┌────────────────────┐
                │      Service       │
                │                    │
                │ ProductService     │
                │ CategoryService    │
                │ FileService        │
                └─────────┬──────────┘
                          │
                          ▼
                ┌────────────────────┐
                │     Repository     │
                │                    │
                │ ProductRepository  │
                │ CategoryRepository │
                └─────────┬──────────┘
                          │
                          ▼
                ┌────────────────────┐
                │   JPA / Hibernate  │
                └─────────┬──────────┘
                          │
                          ▼
                ┌────────────────────┐
                │    H2 Database     │
                └────────────────────┘
```

---

## 📂 Project Structure

```text
src/
└── main/
    ├── java/
    │   └── com/
    │       └── ecommerce/
    │           └── project/
    │               ├── config/
    │               │   ├── AppConfig.java
    │               │   └── AppConstants.java
    │               │
    │               ├── controller/
    │               │   ├── CategoryController.java
    │               │   └── ProductController.java
    │               │
    │               ├── exceptions/
    │               │
    │               ├── model/
    │               │   ├── Category.java
    │               │   └── Product.java
    │               │
    │               ├── payload/
    │               │
    │               ├── repositories/
    │               │   ├── CategoryRepository.java
    │               │   └── ProductRepository.java
    │               │
    │               ├── service/
    │               │   ├── CategoryService.java
    │               │   ├── CategoryServiceImpl.java
    │               │   ├── FileService.java
    │               │   ├── FileServiceImpl.java
    │               │   ├── ProductService.java
    │               │   └── ProductServiceImpl.java
    │               │
    │               └── SbEcomApplication.java
    │
    └── resources/
        └── application.properties
```

---

## 🔄 Application Flow

A typical request follows this flow:

```text
HTTP Request
     │
     ▼
Controller
     │
     ▼
DTO / Payload
     │
     ▼
Service
     │
     ▼
Entity
     │
     ▼
Repository
     │
     ▼
JPA / Hibernate
     │
     ▼
H2 Database
```

For example, when creating a product:

```text
POST /products
      ↓
ProductController
      ↓
ProductService
      ↓
ProductServiceImpl
      ↓
ProductRepository
      ↓
Hibernate
      ↓
H2 Database
```

---

## 🗄️ Database

The project currently uses **H2 Database** for development.

The application is configured to use an in-memory H2 database, which makes it easy to run the project without installing a separate database server.

The persistence layer uses:

```text
Spring Data JPA
        ↓
    Hibernate
        ↓
     H2 DB
```

### H2 Console

The H2 console can be enabled through:

```properties
spring.h2.console.enabled=true
```

---

## ⚙️ Prerequisites

Before running the project, make sure you have installed:

* **JDK 25**
* **Maven**
* **Git**
* **IntelliJ IDEA** or another Java IDE

---

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone https://github.com/Shahbaz-Ahmad98/sb-ecom.git
```

### 2. Navigate to the project

```bash
cd sb-ecom
```

### 3. Build the project

```bash
mvn clean install
```

### 4. Run the application

```bash
mvn spring-boot:run
```

Alternatively, run the main Spring Boot class from IntelliJ IDEA.

---

## 🌐 Application URL

Once the application starts successfully:

```text
http://localhost:8080
```

The backend APIs can be tested using tools such as:

* Postman
* IntelliJ HTTP Client
* cURL
* Frontend applications

---

## 🧪 API Testing

You can use **Postman** to test the REST APIs.

Example request:

```http
POST /api/products
Content-Type: application/json
```

Example request body:

```json
{
  "productName": "iPhone 15",
  "description": "Apple Smartphone",
  "price": 69999,
  "quantity": 10
}
```

The exact endpoint and request structure depend on the current controller implementation.

---

## 📦 Maven

The project uses Maven for dependency management and building the application.

Important dependencies include:

```text
Spring Boot
Spring Web MVC
Spring Data JPA
Hibernate
H2 Database
Lombok
ModelMapper
Hibernate Validator
```

All dependencies are configured in:

```text
pom.xml
```

---

## 🔐 Current Scope

The current version focuses mainly on the backend foundation and product/category functionality.

Future versions can include:

* User registration and login
* Spring Security
* JWT authentication
* Role-based authorization
* Shopping cart
* Wishlist
* Order management
* Payment integration
* Product search
* Product filtering
* Pagination and sorting
* MySQL/PostgreSQL
* Swagger/OpenAPI documentation
* Docker
* Cloud deployment

---

## 🛣️ Future Roadmap

```text
Product & Category
        ↓
Authentication
        ↓
Spring Security + JWT
        ↓
User Management
        ↓
Shopping Cart
        ↓
Order Management
        ↓
Payment Integration
        ↓
MySQL/PostgreSQL
        ↓
Swagger/OpenAPI
        ↓
Docker
        ↓
Cloud Deployment
```

---

## 🎯 Learning Objectives

This project was developed to gain practical experience with:

* Java backend development
* Spring Boot
* REST API development
* Dependency Injection
* Spring MVC
* Spring Data JPA
* Hibernate ORM
* Entity relationships
* DTO pattern
* Repository pattern
* Service layer architecture
* Database persistence
* Validation
* Exception handling
* Maven project management

---

## 👨‍💻 Author

**Shahbaz Ahmed**

Java Backend Developer | Spring Boot

### GitHub

[Shahbaz-Ahmad98](https://github.com/Shahbaz-Ahmad98)

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project is created for learning and educational purposes.
