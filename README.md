# 🛒 ZESTY MART - Online Grocery Mart

<div align="center">

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![JSP](https://img.shields.io/badge/JSP-007396?style=for-the-badge&logo=java&logoColor=white)
![Servlet](https://img.shields.io/badge/Servlet-000000?style=for-the-badge&logo=java&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)

**A modern, full-featured online grocery shopping platform built with Java EE technologies**

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Screenshots](#-screenshots) • [Contributing](#-contributing) • [License](#-license)

</div>

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Database Setup](#-database-setup)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [API Endpoints](#-api-endpoints)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 🎯 About

**ZESTY MART** is a comprehensive online grocery shopping platform that provides a seamless shopping experience for customers and powerful management tools for administrators. Built using Java Enterprise technologies, it offers a robust and scalable solution for e-commerce grocery businesses.

The platform enables users to browse products, manage their shopping cart, complete purchases, and track orders while administrators can manage inventory, users, and analyze business metrics through a dedicated admin panel.

---

## ✨ Features

### 👤 Customer Features
- **User Authentication** - Secure registration and login with password hashing
- **Profile Management** - Update personal information and profile images
- **Product Browsing** - Browse products by categories with search functionality
- **Shopping Cart** - Add, update, and remove items from cart
- **Checkout System** - Complete orders with delivery information
- **Order History** - View past orders and order details
- **Contact Support** - Submit inquiries through contact form
- **Notifications** - Receive updates and notifications

### 🔐 Admin Features
- **Dashboard** - Overview of store statistics and metrics
- **Product Management** - Add, edit, delete products with images
- **Category Management** - Organize products into categories
- **User Management** - View, manage, and delete user accounts
- **Order Management** - Track and manage customer orders
- **Cart Overview** - Monitor customer shopping carts
- **Contact Management** - View and respond to customer inquiries
- **Notification System** - Send notifications to users

### 🛡️ Security Features
- Password hashing for secure authentication
- Session management
- Input validation and sanitization
- Role-based access control (Customer/Admin)

---

## 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| **Backend** | Java EE (Servlets, JSP) |
| **Frontend** | HTML5, CSS3, JavaScript |
| **Database** | MySQL |
| **Server** | Apache Tomcat |
| **Architecture** | MVC (Model-View-Controller) |
| **Build Tool** | Maven (optional) |

---

## 📁 Project Structure

```
ZESTY_MART-Online-Grocery-Mart/
├── java/
│   ├── controller/          # Servlet controllers
│   │   ├── AddProductServlet.java
│   │   ├── AddToCartServlet.java
│   │   ├── CartServlet.java
│   │   ├── CategoryServlet.java
│   │   ├── CheckoutServlet.java
│   │   ├── ContactServlet.java
│   │   ├── LoginServlet.java
│   │   ├── LogoutServlet.java
│   │   ├── ProductServlet.java
│   │   ├── ProfileServlet.java
│   │   ├── RegisterServlet.java
│   │   └── UserManagementServlet.java
│   │
│   ├── dao/                 # Data Access Objects
│   │   ├── BaseDAO.java
│   │   ├── CartDAO.java
│   │   ├── CategoryDAO.java
│   │   ├── ContactDAO.java
│   │   ├── OrderDAO.java
│   │   ├── ProductDAO.java
│   │   └── UserDAO.java
│   │
│   ├── model/               # Entity models
│   │   ├── AddToCart.java
│   │   ├── Category.java
│   │   ├── Contact.java
│   │   ├── Order.java
│   │   ├── Product.java
│   │   └── User.java
│   │
│   └── utils/               # Utility classes
│       ├── DatabaseUtil.java
│       └── PasswordHasher.java
│
├── webapp/
│   ├── css/                 # Stylesheets
│   │   ├── style.css
│   │   ├── shop.css
│   │   └── adminh.css
│   │
│   ├── image/               # Static images
│   │
│   ├── about.jsp            # About page
│   ├── admin.jsp            # Admin dashboard
│   ├── adminproduct.jsp     # Admin product management
│   ├── adminuser.jsp        # Admin user management
│   ├── cart.jsp             # Shopping cart page
│   ├── checkout.jsp         # Checkout page
│   ├── contact.jsp          # Contact page
│   ├── header.jsp           # Common header
│   ├── footer.jsp           # Common footer
│   └── ...                  # Other JSP pages
│
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🚀 Installation

### Prerequisites

Before you begin, ensure you have the following installed:

- **Java JDK** 8 or higher ([Download](https://www.oracle.com/java/technologies/downloads/))
- **Apache Tomcat** 9.x or higher ([Download](https://tomcat.apache.org/download-90.cgi))
- **MySQL** 8.0 or higher ([Download](https://dev.mysql.com/downloads/mysql/))
- **IDE** (Eclipse, IntelliJ IDEA, or VS Code with Java extensions)

### Step-by-Step Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ZESTY_MART-Online-Grocery-Mart.git
   cd ZESTY_MART-Online-Grocery-Mart
   ```

2. **Import the project into your IDE**
   - For Eclipse: `File > Import > Existing Projects into Workspace`
   - For IntelliJ: `File > Open > Select project folder`

3. **Add required libraries**
   - MySQL Connector/J (`mysql-connector-java-8.x.x.jar`)
   - Servlet API (usually included with Tomcat)

4. **Configure Tomcat server in your IDE**

5. **Set up the database** (see [Database Setup](#-database-setup))

6. **Update database configuration** (see [Configuration](#-configuration))

7. **Deploy and run the application**

---

## 🗄️ Database Setup

### Create Database

```sql
CREATE DATABASE onlineGDB;
USE onlineGDB;
```

### Create Tables

```sql
-- Users Table
CREATE TABLE users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    gender VARCHAR(10),
    phone VARCHAR(20) UNIQUE NOT NULL,
    address TEXT,
    password VARCHAR(255) NOT NULL,
    profile_image LONGBLOB,
    profile_image_type VARCHAR(50),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Categories Table
CREATE TABLE categories (
    category_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    description TEXT,
    image VARCHAR(255)
);

-- Products Table
CREATE TABLE products (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(200) NOT NULL,
    category_id INT,
    price DECIMAL(10, 2) NOT NULL,
    stock INT DEFAULT 0,
    description TEXT,
    image VARCHAR(255),
    FOREIGN KEY (category_id) REFERENCES categories(category_id)
);

-- Cart Table
CREATE TABLE cart (
    cart_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    product_id INT,
    quantity INT DEFAULT 1,
    added_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);

-- Orders Table
CREATE TABLE orders (
    order_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    total_amount DECIMAL(10, 2),
    status VARCHAR(50) DEFAULT 'Pending',
    order_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    delivery_address TEXT,
    FOREIGN KEY (user_id) REFERENCES users(user_id)
);

-- Order Details Table
CREATE TABLE order_details (
    detail_id INT PRIMARY KEY AUTO_INCREMENT,
    order_id INT,
    product_id INT,
    quantity INT,
    price DECIMAL(10, 2),
    FOREIGN KEY (order_id) REFERENCES orders(order_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);

-- Contact Messages Table
CREATE TABLE contacts (
    contact_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    email VARCHAR(100),
    subject VARCHAR(200),
    message TEXT,
    is_read BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Notifications Table
CREATE TABLE notifications (
    notification_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    title VARCHAR(200),
    message TEXT,
    is_read BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(user_id)
);
```

### Insert Sample Data (Optional)

```sql
-- Sample Categories
INSERT INTO categories (name, description) VALUES 
('Fruits', 'Fresh fruits and seasonal items'),
('Vegetables', 'Fresh vegetables and greens'),
('Dairy', 'Milk, cheese, and dairy products'),
('Beverages', 'Drinks and refreshments'),
('Snacks', 'Chips, cookies, and snacks');

-- Sample Products
INSERT INTO products (name, category_id, price, stock, description) VALUES 
('Fresh Apples', 1, 3.99, 100, 'Crispy red apples'),
('Organic Bananas', 1, 2.49, 150, 'Organic yellow bananas'),
('Fresh Spinach', 2, 1.99, 80, 'Fresh green spinach leaves'),
('Whole Milk', 3, 4.99, 50, 'Fresh whole milk 1 gallon');
```

---

## ⚙️ Configuration

### Database Configuration

Update the database connection settings in `java/utils/DatabaseUtil.java`:

```java
private static final String URL = "jdbc:mysql://localhost:3306/onlineGDB";
private static final String USER = "your_username";
private static final String PASS = "your_password";
```

### Server Configuration

Ensure your `web.xml` is properly configured with servlet mappings for all controllers.

---

## 📖 Usage

### For Customers

1. **Register** - Create a new account with your details
2. **Login** - Access your account using phone and password
3. **Browse** - Explore products by category or search
4. **Add to Cart** - Select items and add them to your cart
5. **Checkout** - Complete your purchase with delivery details
6. **Track Orders** - View your order history and status

### For Administrators

1. **Access Admin Panel** - Login with admin credentials
2. **Manage Products** - Add, edit, or remove products
3. **Manage Categories** - Organize product categories
4. **View Users** - Monitor registered users
5. **Handle Orders** - Process and update order statuses
6. **Read Messages** - Respond to customer inquiries

---

## 🔗 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/login` | POST | User authentication |
| `/register` | POST | User registration |
| `/logout` | GET | User logout |
| `/products` | GET | List all products |
| `/category` | GET | List categories |
| `/cart` | GET/POST | Manage shopping cart |
| `/checkout` | POST | Process checkout |
| `/profile` | GET/POST | User profile management |
| `/contact` | POST | Submit contact form |
| `/admin/*` | GET/POST | Admin operations |

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Open a Pull Request**

### Contribution Guidelines

- Follow Java coding conventions
- Write clear commit messages
- Update documentation as needed
- Test your changes before submitting

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 Contact

**Project Maintainer:** Kajan

- 📧 Email: your.email@example.com
- 💼 LinkedIn: [Your LinkedIn](https://linkedin.com/in/yourprofile)
- 🐙 GitHub: [@yourusername](https://github.com/yourusername)

---

## 🙏 Acknowledgments

- Thanks to all contributors who have helped improve this project
- Icons and badges from [Shields.io](https://shields.io/)
- Inspiration from modern e-commerce platforms

---

<div align="center">

**⭐ Star this repository if you find it helpful! ⭐**

Made with ❤️ by the ZESTY MART Team

</div>
