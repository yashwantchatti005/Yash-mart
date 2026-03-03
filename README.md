Max


🛒 YashMart - E-Commerce Website
YashMart Banner
HTML5
CSS3
JavaScript
Bootstrap
Java
Spring Boot

📋 Table of Contents
About The Project
Live Demo
Features
Screenshots
Tech Stack
Project Architecture
Getting Started
Prerequisites
Frontend Setup
Backend Setup
API Endpoints
Database Schema
Folder Structure
Contributing
Contact
License
📖 About The Project
YashMart is a full-stack e-commerce web application that provides users with a seamless online shopping experience. The platform allows users to browse products, add items to their cart, manage their wishlist, and complete purchases through a smooth checkout process. Built with a modern tech stack combining a responsive frontend with a robust Java Spring Boot backend and database integration.

🌐 Live Demo
🔗 Frontend Live: https://yashwantchatti005.github.io/Yash-mart/

✨ Features
🛍️ Customer Features
User Registration & Login – Secure authentication and user account management
Product Browsing – Browse through various product categories with detailed descriptions
Search & Filter – Search products by name, category, and apply filters (price, rating, etc.)
Shopping Cart – Add/remove products, update quantities, and view cart summary
Wishlist – Save favorite products for later purchase
Order Placement – Smooth checkout process with order confirmation
Order History – View past orders and track order status
Responsive Design – Optimized for desktop, tablet, and mobile devices
🔧 Admin Features
Product Management – Add, update, and delete products
Category Management – Organize products into categories
Order Management – View and manage customer orders
User Management – Monitor registered users
Dashboard – Overview of sales, orders, and user statistics
🔐 Security Features
User Authentication – Secure login/signup functionality
Session Management – Secure session handling
Input Validation – Both client-side and server-side validation
Password Encryption – Encrypted password storage
📸 Screenshots
Home Page	Product Page
Home	Products
Shopping Cart	Checkout
Cart	Checkout
Replace the placeholder images with actual screenshots of your application.

🛠️ Tech Stack
Frontend
Technology	Purpose
HTML5	Structure & Content
CSS3	Styling & Animations
JavaScript	Interactivity & DOM Manipulation
Bootstrap 5	Responsive UI Framework
Backend
Technology	Purpose
Java	Backend Programming Language
Spring Boot	Application Framework
Spring MVC	Web Layer / REST APIs
Spring Data JPA	Database ORM / Data Access
Hibernate	ORM Implementation
Database
Technology	Purpose
MySQL / H2	Relational Database Management
Spring Data JPA	Database Integration
Tools & Others
Technology	Purpose
Maven	Build & Dependency Management
Git & GitHub	Version Control
GitHub Pages	Frontend Deployment
Postman	API Testing
VS Code / IntelliJ IDEA	IDE
🏗️ Project Architecture
text

┌─────────────────────────────────────────────────────────┐
│                     CLIENT (Browser)                     │
│          HTML5 + CSS3 + JavaScript + Bootstrap            │
└──────────────────────┬──────────────────────────────────┘
                       │  HTTP Requests (REST API)
                       ▼
┌─────────────────────────────────────────────────────────┐
│                  SPRING BOOT APPLICATION                 │
│  ┌─────────────┐  ┌──────────────┐  ┌───────────────┐  │
│  │ Controllers  │→│   Services   │→│  Repositories  │  │
│  │  (REST API)  │  │(Business     │  │  (Data Access) │  │
│  │             │  │  Logic)      │  │               │  │
│  └─────────────┘  └──────────────┘  └───────┬───────┘  │
└─────────────────────────────────────────────┼───────────┘
                                              │ JPA/Hibernate
                                              ▼
                                 ┌─────────────────────┐
                                 │      DATABASE        │
                                 │   (MySQL / H2)       │
                                 └─────────────────────┘
🚀 Getting Started
Prerequisites
Make sure you have the following installed on your system:

Java JDK 17+ – Download
Maven 3.8+ – Download
MySQL 8.0+ (or use H2 for development) – Download
Git – Download
Node.js (optional, for frontend tooling) – Download
Frontend Setup
Bash

# 1. Clone the repository
git clone https://github.com/yashwantchatti005/Yash-mart.git

# 2. Navigate to the project directory
cd Yash-mart

# 3. Open index.html in your browser
# Or use Live Server extension in VS Code
Backend Setup
Bash

# 1. Navigate to the backend directory
cd Yash-mart/backend    # (adjust path based on your project structure)

# 2. Configure Database
# Update src/main/resources/application.properties with your DB credentials

# 3. Build the project
mvn clean install

# 4. Run the Spring Boot application
mvn spring-boot:run

# The backend server will start at http://localhost:8080
Database Configuration (application.properties)
properties

# ========================
# MySQL Configuration
# ========================
spring.datasource.url=jdbc:mysql://localhost:3306/yashmart_db
spring.datasource.username=root
spring.datasource.password=your_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# ========================
# JPA / Hibernate
# ========================
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect

# ========================
# Server Configuration
# ========================
server.port=8080
📡 API Endpoints
👤 User APIs
Method	Endpoint	Description
POST	/api/users/register	Register a new user
POST	/api/users/login	User login
GET	/api/users/{id}	Get user by ID
PUT	/api/users/{id}	Update user details
DELETE	/api/users/{id}	Delete user account
📦 Product APIs
Method	Endpoint	Description
GET	/api/products	Get all products
GET	/api/products/{id}	Get product by ID
GET	/api/products/category/{category}	Get products by category
POST	/api/products	Add a new product (Admin)
PUT	/api/products/{id}	Update product (Admin)
DELETE	/api/products/{id}	Delete product (Admin)
🛒 Cart APIs
Method	Endpoint	Description
GET	/api/cart/{userId}	Get user's cart
POST	/api/cart/add	Add item to cart
PUT	/api/cart/update	Update cart item quantity
DELETE	/api/cart/remove/{itemId}	Remove item from cart
📋 Order APIs
Method	Endpoint	Description
POST	/api/orders	Place a new order
GET	/api/orders/{userId}	Get user's orders
GET	/api/orders/details/{orderId}	Get order details
PUT	/api/orders/{orderId}/status	Update order status (Admin)
🗄️ Database Schema
SQL

-- Users Table
CREATE TABLE users (
    user_id     BIGINT PRIMARY KEY AUTO_INCREMENT,
    username    VARCHAR(50) NOT NULL UNIQUE,
    email       VARCHAR(100) NOT NULL UNIQUE,
    password    VARCHAR(255) NOT NULL,
    full_name   VARCHAR(100),
    phone       VARCHAR(15),
    address     TEXT,
    role        ENUM('CUSTOMER', 'ADMIN') DEFAULT 'CUSTOMER',
    created_at  TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Categories Table
CREATE TABLE categories (
    category_id   BIGINT PRIMARY KEY AUTO_INCREMENT,
    category_name VARCHAR(100) NOT NULL,
    description   TEXT
);

-- Products Table
CREATE TABLE products (
    product_id    BIGINT PRIMARY KEY AUTO_INCREMENT,
    product_name  VARCHAR(200) NOT NULL,
    description   TEXT,
    price         DECIMAL(10,2) NOT NULL,
    stock         INT DEFAULT 0,
    image_url     VARCHAR(500),
    category_id   BIGINT,
    created_at    TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (category_id) REFERENCES categories(category_id)
);

-- Cart Table
CREATE TABLE cart (
    cart_id     BIGINT PRIMARY KEY AUTO_INCREMENT,
    user_id     BIGINT,
    product_id  BIGINT,
    quantity    INT DEFAULT 1,
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);

-- Orders Table
CREATE TABLE orders (
    order_id      BIGINT PRIMARY KEY AUTO_INCREMENT,
    user_id       BIGINT,
    total_amount  DECIMAL(10,2),
    order_status  ENUM('PENDING','PROCESSING','SHIPPED','DELIVERED','CANCELLED') DEFAULT 'PENDING',
    order_date    TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(user_id)
);

-- Order Items Table
CREATE TABLE order_items (
    item_id     BIGINT PRIMARY KEY AUTO_INCREMENT,
    order_id    BIGINT,
    product_id  BIGINT,
    quantity    INT,
    price       DECIMAL(10,2),
    FOREIGN KEY (order_id) REFERENCES orders(order_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);
📁 Folder Structure
text

Yash-mart/
│
├── 📂 frontend/
│   ├── 📄 index.html              # Home page
│   ├── 📄 products.html           # Products listing page
│   ├── 📄 product-detail.html     # Single product details
│   ├── 📄 cart.html               # Shopping cart page
│   ├── 📄 checkout.html           # Checkout page
│   ├── 📄 login.html              # Login page
│   ├── 📄 register.html           # Registration page
│   ├── 📂 css/
│   │   ├── 📄 style.css           # Main stylesheet
│   │   ├── 📄 responsive.css      # Responsive styles
│   │   └── 📄 bootstrap.min.css   # Bootstrap CSS
│   ├── 📂 js/
│   │   ├── 📄 main.js             # Main JavaScript
│   │   ├── 📄 cart.js             # Cart functionality
│   │   ├── 📄 auth.js             # Authentication logic
│   │   └── 📄 api.js              # API calls
│   └── 📂 images/
│       └── ...                     # Product & UI images
│
├── 📂 backend/
│   ├── 📂 src/
│   │   ├── 📂 main/
│   │   │   ├── 📂 java/com/yashmart/
│   │   │   │   ├── 📄 YashMartApplication.java
│   │   │   │   ├── 📂 controller/
│   │   │   │   │   ├── 📄 UserController.java
│   │   │   │   │   ├── 📄 ProductController.java
│   │   │   │   │   ├── 📄 CartController.java
│   │   │   │   │   └── 📄 OrderController.java
│   │   │   │   ├── 📂 model/
│   │   │   │   │   ├── 📄 User.java
│   │   │   │   │   ├── 📄 Product.java
│   │   │   │   │   ├── 📄 Cart.java
│   │   │   │   │   ├── 📄 Order.java
│   │   │   │   │   └── 📄 OrderItem.java
│   │   │   │   ├── 📂 repository/
│   │   │   │   │   ├── 📄 UserRepository.java
│   │   │   │   │   ├── 📄 ProductRepository.java
│   │   │   │   │   ├── 📄 CartRepository.java
│   │   │   │   │   └── 📄 OrderRepository.java
│   │   │   │   ├── 📂 service/
│   │   │   │   │   ├── 📄 UserService.java
│   │   │   │   │   ├── 📄 ProductService.java
│   │   │   │   │   ├── 📄 CartService.java
│   │   │   │   │   └── 📄 OrderService.java
│   │   │   │   └── 📂 config/
│   │   │   │       └── 📄 CorsConfig.java
│   │   │   └── 📂 resources/
│   │   │       ├── 📄 application.properties
│   │   │       └── 📄 data.sql          # Initial data
│   │   └── 📂 test/
│   │       └── ...                       # Unit tests
│   └── 📄 pom.xml                        # Maven dependencies
│
├── 📄 README.md
├── 📄 .gitignore
└── 📄 LICENSE
🤝 Contributing
Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated!

Fork the Project
Create your Feature Branch
Bash

git checkout -b feature/AmazingFeature
Commit your Changes
Bash

git commit -m "Add some AmazingFeature"
Push to the Branch
Bash

git push origin feature/AmazingFeature
Open a Pull Request
📞 Contact
Yashwant Chatti

🔗 GitHub: @yashwantchatti005
🌐 Project Link: https://github.com/yashwantchatti005/Yash-mart
📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

⭐ Show Your Support
If you found this project helpful, please give it a ⭐ on GitHub!
