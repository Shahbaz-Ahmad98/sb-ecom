# 🛒 SB-Ecom — E-Commerce Backend

SB-Ecom is a RESTful E-Commerce backend application built using Java and Spring Boot. The project provides APIs for managing products, categories, users, authentication, shopping carts, and orders.

It is designed as a backend-focused project to demonstrate practical experience with Spring Boot, REST APIs, Spring Data JPA, Hibernate, PostgreSQL, authentication and authorization, pagination, sorting, filtering, exception handling, and layered application architecture.


## 🚀 Features

- 🔐 User Authentication & Authorization
- 👤 User Management
- 📦 Product Management
- 🗂️ Category Management
- 🛒 Shopping Cart Management
- 📋 Order Management
- 🔎 Product Search & Filtering
- 📄 Pagination & Sorting
- 🔄 CRUD REST APIs
- 🗄️ PostgreSQL Database Integration
- 🧩 Spring Data JPA & Hibernate ORM
- ✅ Request Validation
- 📋 DTO-based API Responses
- 🔍 Global Exception Handling
- 🛡️ Role-based Authorization
- 🏗️ Layered Architecture
- 🧪 API Testing using Postman


## 🛠️ Tech Stack

| Technology | Usage |
|------------|-------|
| Java | Core programming language |
| Spring Boot | Backend application framework |
| Spring Web | REST API development |
| Spring Security | Authentication & authorization |
| Spring Data JPA | Database interaction |
| Hibernate | ORM |
| PostgreSQL | Relational database |
| Maven | Dependency management & build |
| Lombok | Boilerplate code reduction |
| ModelMapper | DTO ↔ Entity mapping |
| JWT | Token-based authentication |
| Postman | API testing |
| Git & GitHub | Version control |


## 🏗️ Project Architecture

The project follows a layered architecture to keep the application organized, maintainable, and scalable.

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
│    PostgreSQL    │
└──────────────────┘


### Main Layers

Controller Layer

- Handles HTTP requests.
- Defines REST endpoints.
- Validates and processes incoming requests.
- Returns appropriate HTTP responses.

Service Layer

- Contains business logic.
- Processes application operations.
- Coordinates between controllers and repositories.

Repository Layer

- Communicates with the database.
- Uses Spring Data JPA repositories.
- Handles database operations.

Entity Layer

- Represents database tables using JPA entities.
- Defines relationships between application entities.

DTO Layer

- Defines data exposed through APIs.
- Helps separate API models from database entities.
- Controls the data returned to clients.

Security Layer

- Handles authentication and authorization.
- Uses JWT-based authentication.
- Provides role-based access control for secured operations.


## 📁 Project Structure

src
└── main
    ├── java
    │   └── com.ecommerce.project
    │       ├── config
    │       ├── controller
    │       ├── dto
    │       ├── entities
    │       ├── exceptions
    │       ├── repositories
    │       ├── security
    │       ├── service
    │       ├── util
    │       └── SbEcomApplication.java
    │
    └── resources
        ├── application.properties
        └── static/

The package structure may evolve as the project continues to develop.


# 📦 Core Modules

## 1. Category Management

The category module organizes products into different categories.

### Operations

- Create category
- Get all categories
- Get category by ID
- Update category
- Delete category


## 2. Product Management

The product module manages products available in the store.

### Operations

- Create product
- Get all products
- Get product by ID
- Update product
- Delete product
- Associate products with categories
- Search products
- Filter products
- Pagination
- Sorting


## 3. User Management

The user module handles application users and their information.

### Functionality

- User registration
- User authentication
- User information management
- User-role relationships
- Secured user operations


## 4. Authentication & Authorization

The application uses authentication and authorization mechanisms to secure APIs.

### Authentication

- User registration
- User login
- JWT token generation
- JWT token validation
- Authentication filtering

### Authorization

- Role-based access control
- Protected endpoints
- User and administrator permissions


## 5. Cart Management

The cart module allows users to manage products they intend to purchase.

### Functionality

- Create/manage carts
- Add products to cart
- Update cart items
- Remove cart items
- Retrieve cart information
- Manage product quantities


## 6. Order Management

The order module manages customer orders generated from cart items.

### Functionality

- Create orders
- Retrieve orders
- Manage order information
- Associate orders with users
- Handle ordered products

Order functionality may continue to evolve as additional features are implemented.


## 7. Product Search & Filtering

The application supports finding products based on different criteria.

### Functionality

- Search products
- Filter products
- Category-based product retrieval
- Combined search and filtering operations


## 8. Pagination & Sorting

Large product collections can be handled efficiently using pagination and sorting.

### Functionality

- Paginated product results
- Page size control
- Page number selection
- Sorting by supported fields
- Ascending and descending sorting


# 🗄️ Database

The application uses PostgreSQL as the relational database and JPA/Hibernate for object-relational mapping.

### Main Entities

User
 │
 ├── Cart
 │     │
 │     └── CartItem
 │            │
 │            └── Product
 │                   │
 │                   └── Category
 │
 └── Order
       │
       └── Ordered Products

The relationships between entities are managed using JPA annotations such as:

@Entity
@OneToMany
@ManyToOne
@OneToOne


# 🔗 REST API

The application exposes RESTful APIs for interacting with the e-commerce system.

### Example Endpoint Structure

/api
├── /categories
├── /products
├── /users
├── /auth
├── /carts
└── /orders


### Example Requests

#### Get Categories

GET /api/categories

#### Get Products

GET /api/products

#### Search Products

GET /api/products/search

#### Create Product

POST /api/products

#### Get Cart

GET /api/carts/{cartId}

#### Create Order

POST /api/orders

Endpoint paths may change as the project continues to evolve.


# ⚙️ Getting Started

## Prerequisites

Make sure you have the following installed:

- Java JDK
- Maven
- PostgreSQL
- Git
- IntelliJ IDEA or another Java IDE
- Postman (recommended)


## 📥 Clone the Repository

git clone https://github.com/Shahbaz-Ahmad98/sb-ecom.git

Navigate to the project:

cd sb-ecom


# 🗄️ PostgreSQL Configuration

Create the required database in PostgreSQL:

CREATE DATABASE ecommerce;

Application configuration is maintained in:

src/main/resources/application.properties

Example configuration:

spring.application.name=sb-ecom

spring.datasource.url=jdbc:postgresql://localhost:5432/ecommerce
spring.datasource.username=postgres
spring.datasource.password=YOUR_POSTGRES_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect

Do not commit real database passwords, JWT secrets, or other sensitive credentials to GitHub.


# ▶️ Run the Application

### Using Maven

mvn spring-boot:run

### Or using IntelliJ IDEA

Run:

SbEcomApplication.java

The application runs on:

http://localhost:8080


# 🧪 API Testing

The APIs can be tested using Postman.

### Typical Workflow

1. Start PostgreSQL
          ↓
2. Start Spring Boot application
          ↓
3. Open Postman
          ↓
4. Send API request
          ↓
5. Controller receives request
          ↓
6. Service processes business logic
          ↓
7. Repository communicates with PostgreSQL
          ↓
8. API returns JSON response


# ✅ Current Development Status

## Completed

- [x] Spring Boot project setup
- [x] Product management
- [x] Category management
- [x] JPA/Hibernate integration
- [x] REST APIs
- [x] Authentication
- [x] Authorization
- [x] JWT-based security
- [x] Cart functionality
- [x] DTO implementation
- [x] Repository & service layers
- [x] Request validation
- [x] Exception handling
- [x] API testing with Postman
- [x] Order management
- [x] Product search and filtering
- [x] Pagination and sorting
- [x] Role-based authorization


## Planned Improvements

- [ ] Payment integration
- [ ] API documentation using Swagger/OpenAPI
- [ ] Unit and integration testing
- [ ] Docker containerization
- [ ] Deployment to a cloud platform
- [ ] Frontend integration


# 🔮 Future Scope

The project can be extended into a complete full-stack e-commerce platform by adding:

- React/Angular frontend
- Online payment gateway
- Order tracking
- Wishlist
- Product reviews and ratings
- Email notifications
- Admin dashboard
- Inventory management
- Cloud deployment
- Docker & CI/CD
- Advanced analytics


# 🎯 Learning Objectives

This project was developed to gain practical experience with:

- Java backend development
- Spring Boot
- REST API design
- Spring Security
- JWT authentication
- Role-based authorization
- Spring Data JPA
- Hibernate ORM
- PostgreSQL
- Relational database design
- Entity relationships
- DTOs
- Dependency Injection
- Layered architecture
- Pagination
- Sorting
- Searching and filtering
- Exception handling
- Git & GitHub
- API testing with Postman


# 👨‍💻 Author

Shahbaz Ahmad

Java Backend Developer

### Technologies & Interests

Java
Spring Boot
Spring Security
Spring Data JPA
Hibernate
PostgreSQL
REST APIs
JWT
Git & GitHub
Backend Development


# ⭐ Support

If you find this project useful for learning or reference, consider giving the repository a ⭐ on GitHub.


# 📄 License

This project is intended primarily for learning and educational purposes.
