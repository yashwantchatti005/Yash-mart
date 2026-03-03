# 🛒 YashMart – Full Stack E-Commerce Web Application

---

## 📖 About The Project

YashMart is a full-stack e-commerce web application built using **Java Spring Boot** for the backend and **HTML, CSS, JavaScript, and Bootstrap** for the frontend.

The application provides a complete online shopping experience including:

- User authentication
- Product browsing
- Cart management
- Wishlist functionality
- Order placement
- Admin management dashboard

This project was built to understand real-world e-commerce architecture, REST APIs, role-based authentication, and database relationships.

---

## 🌐 Live Demo

🔗 **Frontend Live:**  
https://yashwantchatti005.github.io/Yash-mart/

Backend runs locally at:  
http://localhost:8080

---

## ✨ Features

### 🛍️ Customer Features

- User Registration & Login
- Add to Cart / Remove from Cart
- Wishlist Management
- Search & Filter Products
- Category-Based Browsing
- Smooth Checkout Process
- Order History Tracking
- Fully Responsive Design

---

### 🔧 Admin Features

- Add / Update / Delete Products
- Category Management
- Order Status Management
- User Management
- Dashboard Overview

---

### 🔐 Security Features

- Password Encryption (BCrypt)
- Input Validation (Client + Server)
- Role-Based Access (ADMIN / CUSTOMER)
- Secure REST API structure

---

## 🛠️ Tech Stack

### 🎨 Frontend

- HTML5
- CSS3
- JavaScript
- Bootstrap 5

---

### ⚙️ Backend

- Java 17
- Spring Boot
- Spring MVC
- Spring Data JPA
- Hibernate
- Maven

---

### 🗄️ Database

- MySQL
- H2 (Development)

---

## 🏗️ Project Architecture

```
CLIENT (Browser)
    │
    ▼
HTML + CSS + JS + Bootstrap
    │
    ▼
REST API Calls
    │
    ▼
Spring Boot Application
    ├── Controller Layer
    ├── Service Layer
    ├── Repository Layer
    │
    ▼
Database (MySQL / H2)
```

Architecture Pattern Used:

- MVC (Model-View-Controller)
- Layered Architecture
- RESTful API Design

---

## 🚀 Getting Started

### ✅ Prerequisites

Make sure you have installed:

- Java JDK 17+
- Maven 3.8+
- MySQL 8.0+
- Git
- VS Code or IntelliJ IDEA

---

### 🖥️ Frontend Setup

```bash
# Clone repository
git clone https://github.com/yashwantchatti005/Yash-mart.git

# Navigate into folder
cd Yash-mart/frontend

# Open index.html in browser
```

---

### ⚙️ Backend Setup

```bash
cd Yash-mart/backend

# Build project
mvn clean install

# Run Spring Boot application
mvn spring-boot:run
```

Backend will start at:

```
http://localhost:8080
```

---

## ⚙️ Database Configuration

Update `application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/yashmart_db
spring.datasource.username=root
spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect

server.port=8080
```

---

## 📡 API Endpoints

### 👤 User APIs

| Method | Endpoint | Description |
|--------|----------|------------|
| POST | /api/users/register | Register user |
| POST | /api/users/login | Login user |
| GET | /api/users/{id} | Get user |
| PUT | /api/users/{id} | Update user |
| DELETE | /api/users/{id} | Delete user |

---

### 📦 Product APIs

| Method | Endpoint |
|--------|----------|
| GET | /api/products |
| GET | /api/products/{id} |
| GET | /api/products/category/{category} |
| POST | /api/products (Admin) |
| PUT | /api/products/{id} (Admin) |
| DELETE | /api/products/{id} (Admin) |

---

### 🛒 Cart APIs

| Method | Endpoint |
|--------|----------|
| GET | /api/cart/{userId} |
| POST | /api/cart/add |
| PUT | /api/cart/update |
| DELETE | /api/cart/remove/{itemId} |

---

### 📋 Order APIs

| Method | Endpoint |
|--------|----------|
| POST | /api/orders |
| GET | /api/orders/{userId} |
| GET | /api/orders/details/{orderId} |
| PUT | /api/orders/{orderId}/status (Admin) |

---

## 📁 Folder Structure

```
Yash-mart/
│
├── frontend/
│   ├── index.html
│   ├── products.html
│   ├── cart.html
│   ├── checkout.html
│   ├── css/
│   ├── js/
│   └── images/
│
├── backend/
│   ├── controller/
│   ├── service/
│   ├── repository/
│   ├── model/
│   ├── config/
│   └── application.properties
│
└── README.md
```

---

## 🚀 Future Improvements

- JWT Authentication
- Payment Gateway Integration (Razorpay / Stripe)
- Product Reviews & Ratings
- Admin Analytics Dashboard
- Docker Deployment
- Cloud Deployment (AWS / Render)

---

## 🤝 Contributing

1. Fork the Project  
2. Create your Feature Branch  

```bash
git checkout -b feature/AmazingFeature
```

3. Commit your Changes  

```bash
git commit -m "Add AmazingFeature"
```

4. Push to the Branch  

```bash
git push origin feature/AmazingFeature
```

5. Open a Pull Request  

---

## 📞 Contact

**Yashwant Chatti**

GitHub:  
https://github.com/yashwantchatti005  

Project Link:  
https://github.com/yashwantchatti005/Yash-mart  

---

## 📄 License

This project is licensed under the MIT License.

---

## ⭐ Show Your Support

If you found this project helpful, please give it a ⭐ on GitHub!
