# 🛒 E-Commerce Backend API

This is a fully functional **Spring Boot E-Commerce Backend** application with JWT authentication, product and image management, cart operations, and order processing. Built for showcasing backend development skills, especially for Java backend developer roles.

---

## 🚀 Features

- ✅ **User Registration & Login** (JWT based)
- 🛡️ **Spring Security** authentication
- 📦 **Product CRUD** (Create, Read, Update, Delete)
- 🖼️ Upload & serve **product images**
- 🛍️ **Shopping Cart**: Add/Remove/View items
- 📦 **Place Orders**: Order history for each user
- 🔐 Role-based authorization (ADMIN, USER)
- 📁 File storage for uploaded images
- 🗂️ MySQL database with JPA & Hibernate

---

## 📂 Tech Stack

- **Java 17**
- **Spring Boot**
- **Spring Security + JWT**
- **Spring Data JPA**
- **MySQL**
- **Maven**
- **Postman** (for testing)

---

## 🔧 Setup Instructions

### 1. Clone the repository

git clone https://github.com/yourusername/ecommerce-backend.git
cd ecommerce-backend
### 2. Configure application.properties

# Database
spring.datasource.url=jdbc:mysql://localhost:3306/ecommerce
spring.datasource.username=root
spring.datasource.password=yourpassword

# JPA
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# JWT Secret
jwt.secret=your_jwt_secret_key

# Static files (for product images)
spring.web.resources.static-locations=file:uploads/
### 3. Create Uploads Directory

mkdir uploads
### 4. Run the Application

./mvnw spring-boot:run
The backend will run at: http://localhost:8080

### 🔑 Authentication
Register: POST /api/auth/register

Login: POST /api/auth/login

After login, use the token in headers:


Authorization: Bearer <your_jwt_token>
### 📦 API Endpoints
### 🔐 Auth
Method	Endpoint	Description

POST	/api/auth/register	Register user

POST	/api/auth/login	Login & get token

### 📦 Products
Method	Endpoint	Description
GET	/api/products/all	Get all products
GET	/api/products/{id}	Get product by ID
POST	/api/products/add	Add new product (admin)
PUT	/api/products/{id}	Update product (admin)
DELETE	/api/products/{id}	Delete product (admin)

### 🛒 Cart
Method	Endpoint	Description
POST	/api/cart/add	Add to cart
GET	/api/cart/all	Get user cart items
DELETE	/api/cart/remove	Remove one product
DELETE	/api/cart/clear	Clear entire cart

### 📦 Orders
Method	Endpoint	Description
POST	/api/orders/place	Place new order
GET	/api/orders/my	Get logged in user's orders
DELETE	/api/orders/{id}	Delete order

### 🖼️ Uploading & Serving Images
When uploading a product, image is stored in uploads/ directory.

Served statically via:

http://localhost:8080/uploads/{filename}

### 🧑‍💻 Roles
USER - Can view, add to cart, and place orders

ADMIN - Can manage all products

