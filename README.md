# 🛒 SB-Ecom — E-Commerce Backend

<p align="center">
  <b>A RESTful E-Commerce Backend built with Java, Spring Boot, Spring Security, JPA/Hibernate, and PostgreSQL.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Java-Backend-orange?style=for-the-badge&logo=openjdk" alt="Java"/>
  <img src="https://img.shields.io/badge/Spring%20Boot-Backend-brightgreen?style=for-the-badge&logo=springboot" alt="Spring Boot"/>
  <img src="https://img.shields.io/badge/Spring%20Security-Authentication-green?style=for-the-badge&logo=springsecurity" alt="Spring Security"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-blue?style=for-the-badge&logo=postgresql" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/JPA%2FHibernate-ORM-brown?style=for-the-badge" alt="JPA Hibernate"/>
  <img src="https://img.shields.io/badge/Postman-API%20Testing-orange?style=for-the-badge&logo=postman" alt="Postman"/>
  <img src="https://img.shields.io/badge/Swagger%2FOpenAPI-API%20Documentation-green?style=for-the-badge&logo=swagger" alt="Swagger/OpenAPI"/>
</p>

---

## 📌 About the Project

**SB-Ecom** is a backend-focused **E-Commerce REST API application** developed using **Java and Spring Boot**.

The application provides APIs for managing:

* Users
* Authentication
* Authorization
* Products
* Categories
* Shopping carts
* Addresses
* Orders
* Payments

The project demonstrates practical implementation of **REST API development, Spring Security, JWT authentication, role-based authorization, Spring Data JPA, Hibernate ORM, PostgreSQL, DTOs, validation, exception handling, pagination, sorting, product search, filtering, order processing, payment data management, and Swagger/OpenAPI documentation**.

The project follows a **layered architecture** to maintain separation of concerns and make the application easier to maintain and extend.

---

## ✨ Key Features

### 🔐 Authentication & Security

* User registration
* User login
* JWT-based authentication
* JWT token validation
* Authentication filter
* Role-based authorization
* Protected REST endpoints

### 👤 User Management

* User registration
* User authentication
* User information management
* User-role relationships

### 📦 Product Management

* Create products
* Retrieve products
* Retrieve product by ID
* Update products
* Delete products
* Associate products with categories

### 🔎 Product Search & Filtering

* Search products
* Filter products
* Category-based filtering
* Combined search and filtering operations

### 📄 Pagination & Sorting

* Paginated product results
* Page number selection
* Page size control
* Ascending sorting
* Descending sorting

### 🗂️ Category Management

* Create categories
* Retrieve all categories
* Retrieve category by ID
* Update categories
* Delete categories

### 🛒 Cart Management

* Create and manage carts
* Add products to cart
* Update cart items
* Remove cart items
* Manage product quantities
* Retrieve cart details

### 🏠 Address Management

* Create user addresses
* Retrieve user addresses
* Update addresses
* Delete addresses
* Address validation
* Associate addresses with users

### 📋 Order Management

* Create orders
* Retrieve orders
* Manage order information
* Associate orders with users
* Handle ordered products
* Manage order items

### 💳 Payment Management

* Create payment records
* Store payment gateway details
* Store payment ID
* Track payment status
* Store payment response message
* Associate payment with order

### 🧩 Additional Features

* CRUD REST APIs
* DTO-based API responses
* Request validation
* Global exception handling
* Layered architecture
* PostgreSQL database integration
* Address management
* Order and payment processing
* API testing using Postman
* Swagger / OpenAPI documentation

---

## 🛠️ Technology Stack

| Technology            | Purpose                         |
| --------------------- | ------------------------------- |
| **Java**              | Core programming language       |
| **Spring Boot**       | Backend application framework   |
| **Spring Web**        | REST API development            |
| **Spring Security**   | Authentication & authorization  |
| **JWT**               | Token-based authentication      |
| **Spring Data JPA**   | Database interaction            |
| **Hibernate**         | ORM / persistence               |
| **PostgreSQL**        | Relational database             |
| **Maven**             | Build and dependency management |
| **Lombok**            | Boilerplate code reduction      |
| **ModelMapper**       | DTO ↔ Entity mapping            |
| **Postman**           | API testing                     |
| **Swagger / OpenAPI** | API documentation               |
| **Git**               | Version control                 |
| **GitHub**            | Source code hosting             |

---

## 🏗️ Architecture

SB-Ecom follows a **layered backend architecture**.

```text
                    Client / Postman
                           │
                           ▼
                 ┌──────────────────┐
                 │    Controller    │
                 │     Layer        │
                 └────────┬─────────┘
                          │
                          ▼
                 ┌──────────────────┐
                 │     Service      │
                 │      Layer       │
                 └────────┬─────────┘
                          │
                          ▼
                 ┌──────────────────┐
                 │    Repository    │
                 │      Layer       │
                 └────────┬─────────┘
                          │
                          ▼
                 ┌──────────────────┐
                 │    PostgreSQL    │
                 │     Database     │
                 └──────────────────┘
```

### Architectural Layers

#### Controller Layer

Responsible for:

* Handling HTTP requests
* Defining REST endpoints
* Processing request data
* Returning API responses

#### Service Layer

Responsible for:

* Business logic
* Application operations
* Coordinating between controllers and repositories

#### Repository Layer

Responsible for:

* Database operations
* Data persistence
* Communication with PostgreSQL through Spring Data JPA

#### Entity Layer

Responsible for:

* Representing database tables
* Defining entity relationships
* Mapping Java objects to database records

#### DTO Layer

Responsible for:

* API request and response models
* Separating API models from database entities
* Controlling exposed data

#### Security Layer

Responsible for:

* Authentication
* JWT processing
* Authorization
* Role-based access control
* Securing protected endpoints

---

## 📁 Project Structure

```text
src/
└── main/
    ├── java/
    │   └── com.ecommerce.project/
    │       ├── config/
    │       ├── controller/
    │       ├── dto/
    │       ├── entities/
    │       ├── exceptions/
    │       ├── repositories/
    │       ├── security/
    │       ├── service/
    │       ├── util/
    │       └── SbEcomApplication.java
    │
    └── resources/
        ├── application.properties
        └── static/
```

> The project structure may evolve as additional features are implemented.

---

## 📦 Core Modules

### 1. Category Module

Manages product categories and their associated operations.

```text
Create Category
Get Categories
Get Category by ID
Update Category
Delete Category
```

---

### 2. Product Module

Handles product creation, retrieval, modification, deletion, and category association.

```text
Create Product
Get Products
Get Product by ID
Update Product
Delete Product
Search
Filtering
Pagination
Sorting
```

---

### 3. Authentication Module

Handles user authentication and JWT-based security.

```text
Register
Login
JWT Generation
JWT Validation
Authentication Filter
```

---

### 4. Authorization Module

Controls access to protected resources using user roles.

```text
Role-Based Access
Protected Endpoints
User Permissions
Administrator Permissions
```

---

### 5. Cart Module

Allows users to manage the products they intend to purchase.

```text
Create Cart
Add Product
Update Cart Item
Remove Cart Item
Update Quantity
Retrieve Cart
```

---

### 6. Address Module

Handles user address creation, updating, validation, and persistence.

```text
Create Address
Update Address
Retrieve Address
Delete Address
Associate Address with User
```

---

### 7. Order Module

Handles customer orders and order-related information.

```text
Create Order
Retrieve Orders
Manage Order Information
Associate Orders with Users
Handle Ordered Products
Manage Order Items
Create Payment Record
Store Payment Gateway Details
Store Payment ID
Track Payment Status
Store Payment Response
Associate Payment with Order
```

---

### 8. Search, Filtering & Pagination

Provides efficient product retrieval capabilities.

```text
Search Products
Filter Products
Category Filtering
Pagination
Sorting
```

---

## 🗄️ Database Design

The application uses **PostgreSQL** as its relational database with **JPA/Hibernate** for ORM.

### Main Entity Relationships

```text
                    ┌──────────────┐
                    │     User     │
                    └──────┬───────┘
                           │
              ┌────────────┼────────────┐
              │            │            │
              ▼            ▼            ▼
        ┌──────────┐  ┌──────────┐  ┌──────────┐
        │   Cart   │  │  Order   │  │   Role   │
        └────┬─────┘  └────┬─────┘  └──────────┘
             │             │
             ▼             ▼
        ┌──────────┐  ┌──────────────┐
        │ CartItem │  │ OrderedItems │
        └────┬─────┘  └──────┬───────┘
             │               │
             └───────┬───────┘
                     ▼
                ┌───────────┐
                │  Product  │
                └─────┬─────┘
                      │
                      ▼
                ┌───────────┐
                │ Category  │
                └───────────┘
```

Entity relationships are implemented using JPA annotations such as:

```java
@Entity
@OneToOne
@OneToMany
@ManyToOne
```

---

## 🔗 REST API

The application exposes RESTful APIs for interacting with the e-commerce system.

### Swagger / OpenAPI Documentation

The project includes **Swagger / OpenAPI documentation** for exploring and testing the available REST APIs.

### API Structure

```text
/api
├── /auth
├── /users
├── /categories
├── /products
├── /carts
├── /addresses
└── /orders
```

### Example Endpoints

#### Authentication

```http
POST /api/auth/signup
POST /api/auth/signin
```

#### Categories

```http
GET    /api/categories
POST   /api/categories
GET    /api/categories/{categoryId}
PUT    /api/categories/{categoryId}
DELETE /api/categories/{categoryId}
```

#### Products

```http
GET    /api/products
POST   /api/products
GET    /api/products/{productId}
PUT    /api/products/{productId}
DELETE /api/products/{productId}
```

#### Cart

```http
GET    /api/carts/{cartId}
POST   /api/carts
PUT    /api/carts/{cartId}
```

#### Addresses

```http
POST   /api/addresses
GET    /api/addresses
PUT    /api/addresses/{addressId}
DELETE /api/addresses/{addressId}
```

#### Orders & Payments

```http
POST /api/orders
GET  /api/orders
GET  /api/orders/{orderId}
POST /api/order/users/payments/{paymentMethod}
```

> Endpoint names may change as the project continues to evolve. Refer to the controllers in the source code for the current API definitions.

---

## ⚙️ Getting Started

### Prerequisites

Install the following software before running the project:

* Java JDK
* Maven
* PostgreSQL
* Git
* IntelliJ IDEA or another Java IDE
* Postman

---

## 📥 Clone the Repository

```bash
git clone https://github.com/Shahbaz-Ahmad98/sb-ecom.git
```

Navigate to the project directory:

```bash
cd sb-ecom
```

---

## 🗄️ PostgreSQL Setup

Create the application database:

```sql
CREATE DATABASE ecommerce;
```

Verify the database:

```sql
\l
```

Connect to the database:

```sql
\c ecommerce
```

---

## 🔧 Application Configuration

Application configuration is located at:

```text
src/main/resources/application.properties
```

Example PostgreSQL configuration:

```properties
spring.application.name=sb-ecom

spring.datasource.url=jdbc:postgresql://localhost:5432/ecommerce
spring.datasource.username=postgres
spring.datasource.password=YOUR_POSTGRES_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
```

> Replace `YOUR_POSTGRES_PASSWORD` with your local PostgreSQL password.

> Never commit real passwords, JWT secrets, or other sensitive credentials to GitHub.

---

## ▶️ Running the Application

### Using Maven

```bash
mvn spring-boot:run
```

### Using IntelliJ IDEA

Run:

```text
SbEcomApplication.java
```

The application will be available at:

```text
http://localhost:8080
```

---

## 🧪 API Testing

Postman can be used to test the REST APIs.

Swagger / OpenAPI documentation can also be used to explore and test the available API endpoints.

### Typical Request Flow

```text
Postman
   │
   ▼
Controller
   │
   ▼
Service
   │
   ▼
Repository
   │
   ▼
PostgreSQL
   │
   ▼
JSON Response
```

---

## 🔐 Security

The project implements security using **Spring Security and JWT**.

### Security Flow

```text
User
  │
  ▼
Login / Registration
  │
  ▼
Authentication
  │
  ▼
JWT Token
  │
  ▼
Request with Token
  │
  ▼
JWT Validation
  │
  ▼
Role / Authorization Check
  │
  ▼
Protected API
```

The security layer contains functionality for:

* JWT generation
* JWT validation
* Authentication filtering
* Role-based authorization
* Secured API endpoints

---

## ✅ Current Development Status

### Completed

* [x] Spring Boot project setup
* [x] REST API development
* [x] Product management
* [x] Category management
* [x] User management
* [x] Authentication
* [x] JWT-based security
* [x] Role-based authorization
* [x] Cart functionality
* [x] Address management
* [x] Order management
* [x] Order item management
* [x] Payment processing
* [x] Payment data persistence
* [x] Product search
* [x] Product filtering
* [x] Pagination
* [x] Sorting
* [x] DTO implementation
* [x] Repository and service layers
* [x] Request validation
* [x] Exception handling
* [x] PostgreSQL integration
* [x] JPA/Hibernate integration
* [x] API testing with Postman
* [x] Swagger / OpenAPI documentation

### 🚧 Planned Improvements

* [ ] External payment gateway integration
* [ ] Unit testing
* [ ] Integration testing
* [ ] Docker containerization
* [ ] CI/CD pipeline
* [ ] Cloud deployment
* [ ] Frontend integration

---

## 🔮 Future Scope

SB-Ecom can be extended into a complete full-stack e-commerce platform with features such as:

* 🌐 React or Angular frontend
* 💳 Online payment gateway
* 📦 Order tracking
* ❤️ Wishlist
* ⭐ Product reviews and ratings
* 📧 Email notifications
* 🧑‍💼 Admin dashboard
* 📊 Inventory management
* ☁️ Cloud deployment
* 🐳 Docker and CI/CD
* 📈 Advanced analytics

---

## 📚 Learning Objectives

This project provides practical experience with:

* Java backend development
* Spring Boot
* Spring Web
* Spring Security
* JWT authentication
* Role-based authorization
* REST API development
* Spring Data JPA
* Hibernate ORM
* PostgreSQL
* Relational database design
* Entity relationships
* Address management
* Order and payment processing
* DTOs
* Dependency Injection
* Layered architecture
* Product search and filtering
* Pagination and sorting
* Request validation
* Exception handling
* API testing
* Swagger / OpenAPI documentation

---

## 💡 What This Project Demonstrates

SB-Ecom demonstrates how a backend application can be structured using:

```text
Clean Separation of Concerns
          +
RESTful API Design
          +
Business Logic
          +
Database Persistence
          +
Authentication & Authorization
          +
Validation & Exception Handling
          +
Scalable Application Structure
```

---

## 👨‍💻 Author

### Shahbaz Ahmad

**Java Backend Developer**

#### Technologies & Interests

```text
Java
Spring Boot
Spring Security
Spring Data JPA
Hibernate
PostgreSQL
REST APIs
JWT
Swagger / OpenAPI
Backend Development
```

---

## ⭐ Support

If you find this project useful for learning or reference, consider giving the repository a ⭐ on GitHub.

---

## 📄 Project Purpose

This project is primarily developed for **learning, practice, and demonstrating backend development skills** with Java and Spring Boot.
