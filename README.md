# 🛒 SB-Ecom — E-Commerce Backend

SB-Ecom is a **RESTful E-Commerce backend application** built using **Java and Spring Boot**. The project provides APIs for managing products, categories, users, authentication, shopping carts, and orders.

It is designed as a backend-focused project to demonstrate practical experience with **Spring Boot, REST APIs, Spring Data JPA, Hibernate, PostgreSQL, JWT authentication, role-based authorization, product search and filtering, pagination, sorting, exception handling, request validation, and layered application architecture**.

---

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
- 📋 DTO-Based API Responses
- 🔍 Exception Handling
- 🛡️ Role-Based Authorization
- 🏗️ Layered Architecture
- 🧪 API Testing using Postman

---

## 🛠️ Tech Stack

| Technology | Usage |
|------------|-------|
| **Java** | Core programming language |
| **Spring Boot** | Backend application framework |
| **Spring Web** | REST API development |
| **Spring Security** | Authentication & authorization |
| **Spring Data JPA** | Database interaction |
| **Hibernate** | ORM |
| **PostgreSQL** | Relational database |
| **JWT** | Token-based authentication |
| **Maven** | Dependency management & build |
| **Lombok** | Boilerplate code reduction |
| **ModelMapper** | DTO ↔ Entity mapping |
| **Postman** | API testing |
| **Git & GitHub** | Version control |

---

## 🏗️ Project Architecture

The project follows a **layered architecture** to keep the application organized, maintainable, and scalable.

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
│    PostgreSQL    │
└──────────────────┘
```

### Main Layers

**Controller Layer**

- Handles HTTP requests.
- Defines REST endpoints.
- Processes client requests.
- Returns appropriate HTTP responses.

**Service Layer**

- Contains business logic.
- Processes application operations.
- Coordinates application workflows.

**Repository Layer**

- Communicates with the database.
- Uses Spring Data JPA repositories.
- Handles database operations.

**Entity Layer**

- Represents database tables using JPA entities.
- Defines relationships between application entities.

**DTO Layer**

- Defines the data exposed through APIs.
- Helps separate API models from database entities.
- Controls request and response data.

**Security Layer**

- Handles authentication and authorization.
- Uses JWT-based authentication.
- Provides role-based access control.
- Secures protected API endpoints.

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

> The package structure may evolve as the project continues to develop.

---

# 📦 Core Modules

## 1. Category Management

The category module allows the application to organize products into different categories.

### Operations

- Create category
- Get all categories
- Get category by ID
- Update category
- Delete category

---

## 2. Product Management

The product module handles the products available in the store.

### Operations

- Create product
- Get products
- Get product by ID
- Update product
- Delete product
- Associate products with categories
- Search products
- Filter products
- Pagination
- Sorting

---

## 3. User Management

The user module handles application users and their information.

### Functionality

- User registration
- User authentication
- User information management
- User-role relationships
- Secured user operations

---

## 4. Authentication & Authorization

The application provides authentication and authorization mechanisms to secure application operations.

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
- Secured operations based on assigned roles

---

## 5. Cart Management

The cart module allows users to manage products they intend to purchase.

### Functionality

- Create and manage carts
- Add products to cart
- Update cart items
- Remove cart items
- Retrieve cart information
- Manage cart quantities

---

## 6. Order Management

The order module manages customer orders.

### Functionality

- Create orders
- Retrieve orders
- Manage order information
- Associate orders with users
- Handle ordered products

---

## 7. Product Search & Filtering

The application supports searching and filtering products based on different criteria.

### Functionality

- Search products
- Filter products
- Category-based filtering
- Search and filtering operations

---

## 8. Pagination & Sorting

The application uses pagination and sorting to efficiently handle product collections.

### Functionality

- Paginated product results
- Page number selection
- Page size control
- Sorting by supported fields
- Ascending and descending sorting

---

## 🗄️ Database

The application uses **PostgreSQL** as the relational database and **JPA/Hibernate** for object-relational mapping.

### Main Entities

```text
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

### Example Endpoint Structure

```text
/api
├── /categories
├── /products
├── /users
├── /auth
├── /carts
└── /orders
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

#### Create Order

```http
POST /api/orders
```

> Endpoint paths may change as the project continues to evolve.

---

## ⚙️ Getting Started

### Prerequisites

Make sure you have the following installed:

- Java JDK
- Maven
- PostgreSQL
- Git
- IntelliJ IDEA or another Java IDE
- Postman (recommended)

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

## 🗄️ PostgreSQL Configuration

Create the required database in PostgreSQL:

```sql
CREATE DATABASE ecommerce;
```

Application configuration is maintained in:

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
>
> Do not commit real database passwords, JWT secrets, or other sensitive credentials to GitHub.

---

## ▶️ Run the Application

### Using Maven

```bash
mvn spring-boot:run
```

### Or using IntelliJ IDEA

Run:

```text
SbEcomApplication.java
```

The application runs on:

```text
http://localhost:8080
```

---

## 🧪 API Testing

The APIs can be tested using **Postman**.

### Typical Workflow

```text
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
```

---

## 📌 Current Development Status

### ✅ Completed

- [x] Spring Boot project setup
- [x] Product management
- [x] Category management
- [x] JPA/Hibernate integration
- [x] REST APIs
- [x] User management
- [x] Authentication
- [x] JWT-based security
- [x] Authorization
- [x] Role-based authorization
- [x] Cart functionality
- [x] Order management
- [x] Product search
- [x] Product filtering
- [x] Pagination
- [x] Sorting
- [x] DTO implementation
- [x] Repository & service layers
- [x] Request validation
- [x] Exception handling
- [x] API testing with Postman
- [x] PostgreSQL database integration

### 🚧 Planned Improvements

- [ ] Payment integration
- [ ] API documentation using Swagger/OpenAPI
- [ ] Unit testing
- [ ] Integration testing
- [ ] Docker containerization
- [ ] CI/CD pipeline
- [ ] Cloud deployment
- [ ] Frontend integration

---

## 🔮 Future Scope

The project can be extended into a complete full-stack e-commerce platform by adding:

- React or Angular frontend
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

---

## 🎯 Learning Objectives

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
- Product search and filtering
- Pagination and sorting
- Exception handling
- Request validation
- Git & GitHub
- API testing with Postman

---

## 👨‍💻 Author

**Shahbaz Ahmad**

**Java Backend Developer**

### Technologies & Interests

```text
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
```

---

## ⭐ Support

If you find this project useful for learning or reference, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project is intended primarily for **learning and educational purposes**.
