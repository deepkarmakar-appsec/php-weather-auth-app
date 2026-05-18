# 🌦️ PHP Weather Auth App

> Secure PHP weather dashboard application focused on authentication security, session protection, server-side API proxying, and secure web development practices.

---

<img width="1604" height="911" alt="login" src="https://github.com/user-attachments/assets/336f03f0-7dcd-47e7-9917-acfb9abad0a5" />

<img width="1594" height="907" alt="register" src="https://github.com/user-attachments/assets/9c5f54b8-9aed-479f-b89e-7e8d33df5943" />

<img width="1579" height="840" alt="dashboard" src="https://github.com/user-attachments/assets/075a16f3-5b02-4026-ba2a-7a5f0e47cce7" />

---

# 🌐 Overview

PHP Weather Auth App is a secure weather dashboard application built using PHP and MySQL with emphasis on authentication security, secure session handling, and protected backend API communication.

The project explores how secure PHP applications can implement:

- User authentication & authorization
- Secure session management
- CSRF protection
- SQL injection prevention
- XSS mitigation
- Secure API proxy architecture
- Environment-based secret management
- Protected dashboard routing

---

# 🔥 Security Highlights

- Secure authentication system with protected dashboard routes
- Session fixation prevention using session regeneration
- CSRF token validation for sensitive actions
- PDO prepared statements for SQL injection prevention
- Secure password hashing using `password_hash()` and `password_verify()`
- Secure backend API proxy for hiding external API keys
- Secure session cookie configuration (`HttpOnly`, `Secure`, `SameSite`)
- Account lockout protection against brute-force attempts
- Output escaping to reduce XSS risks
- Environment-based secret management using `.env`

---

# 🚀 Core Features

## 🔐 Authentication & Session Security

- User registration & login system
- Session-based authentication
- Protected dashboard routes
- Logout session cleanup
- Session regeneration after login
- Account lockout protection
- Secure cookie handling

---

## 🌦️ Weather Dashboard

- Real-time weather data
- Dynamic city search
- Responsive dashboard interface
- Backend weather API integration
- Secure server-side API proxy

---

## 🛡️ Security Controls

The application implements protections against:

- SQL Injection (SQLi)
- Cross-Site Scripting (XSS)
- Session fixation attacks
- CSRF attacks
- Credential stuffing
- Brute-force login attempts

Security mechanisms include:

- PDO prepared statements
- CSRF token validation
- Secure session cookies
- Output escaping
- Input validation
- Session regeneration
- Environment variable protection

---

# 🌐 Application Flow

```text
User
↓
Login/Register
↓
CSRF Validation
↓
Password Verification
↓
Secure Session Created
↓
Dashboard Access
↓
Weather API Request
↓
Server-side API Proxy
↓
OpenWeather API
↓
Secure Weather Response
```

---

# 🔐 Authentication Security Flow

```text
Login Request
↓
CSRF Token Validation
↓
Input Validation
↓
Fetch User From Database
↓
password_verify()
↓
session_regenerate_id()
↓
Dashboard Access
```

---

# 🌦️ API Security Flow

```text
Frontend Request
↓
PHP API Proxy
↓
Input Validation
↓
Secure API Call
↓
OpenWeather API
↓
Filtered Response
↓
Frontend Dashboard
```

---

# 🔥 Security Architecture

```text
Browser
↓
HTTPS Request
↓
PHP Application
↓
Authentication Layer
↓
Session Validation
↓
API Proxy Layer
↓
MySQL Database
↓
External Weather API
```

---

# 🛡️ Security Features Explained

## SQL Injection Protection

Implemented parameterized database queries using PDO prepared statements to reduce SQL injection risks.

```php
$stmt = $con->prepare("SELECT * FROM users WHERE email = ?");
```

---

## Password Security

Passwords are securely hashed and verified using PHP password hashing functions.

```php
password_hash()
password_verify()
```

---

## Session Security

Session identifiers are regenerated after authentication to reduce session fixation risks.

```php
session_regenerate_id(true)
```

Prevents:

- Session fixation
- Session hijacking

---

## CSRF Protection

Sensitive requests validate CSRF tokens before processing.

```php
hash_equals($_SESSION['csrf_token'], $_POST['csrf_token'])
```

---

## Secure Session Cookies

Secure cookie configurations include:

```text
HttpOnly
SameSite
Secure
```

Benefits include:

- Reduced JavaScript cookie access
- Reduced CSRF exposure
- HTTPS-only cookie transmission

---

## XSS Protection

User-controlled output is escaped before rendering in the browser.

```php
htmlspecialchars()
```

Helps reduce:

- Reflected XSS
- Stored XSS

---

## Environment-Based Secret Management

Sensitive credentials and API keys are stored using environment variables.

Protected secrets include:

- Database credentials
- Weather API keys

---

# 📂 Project Structure

```text
project/
│
├── auth/
│   ├── login.php
│   ├── register.php
│   └── logout.php
│
├── dashboard/
│   └── weather.php
│
├── api/
│   └── weather-proxy.php
│
├── includes/
│   ├── db.php
│   ├── session.php
│   ├── csrf.php
│   └── auth-check.php
│
├── assets/
│   ├── css/
│   └── js/
│
├── .env
└── index.php
```

---

# ⚙️ Tech Stack

| Technology | Usage |
|---|---|
| PHP | Backend |
| MySQL | Database |
| HTML5 | Frontend Structure |
| CSS3 | Styling |
| JavaScript | Frontend Interactivity |
| XAMPP | Local Development |
| OpenWeather API | Weather Data |

---

# 🌐 API Integration

## OpenWeather API

Weather data is retrieved securely through a backend API proxy.

Security design includes:

- API key hidden from frontend
- Server-side API communication
- Input validation
- SSL verification enabled

---

# 🔥 Protected Dashboard Flow

```text
Unauthenticated User
↓
Blocked Access
↓
Redirect to Login

Authenticated User
↓
Session Validation
↓
Dashboard Access Granted
```

---

# 🔐 Session Security Model

```text
Login Success
↓
Session Created
↓
Session Regenerated
↓
Secure Cookie Set
↓
Protected Route Access
```

---

# 🚀 Local Setup

## Clone Repository

```bash
git clone https://github.com/deepkarmakar-appsec/php-weather-auth-app.git
```

---

## Configure Environment

Create `.env` file:

```env
DB_HOST=localhost
DB_NAME=weatherapp
DB_USER=root
DB_PASS=password

OPENWEATHER_API_KEY=YOUR_API_KEY
```

---

## Import Database

Import MySQL database using phpMyAdmin or MySQL CLI.

---

## Start Local Server

```text
Apache + MySQL via XAMPP
```

---

# 🧠 Security Concepts Implemented

- Authentication
- Authorization
- Session Security
- CSRF Protection
- SQL Injection Prevention
- XSS Mitigation
- API Proxy Security
- Environment Security
- Secure Cookie Handling
- Brute-force Protection

---

# 🤝 Contribution

Pull requests and improvements are welcome.

Areas for improvement include:

- Security enhancements
- Performance optimization
- UI/UX improvements
- Additional API integrations

---

# 💡 Author

## Deep Karmakar

Security-focused Developer  
Application Security • DevSecOps • Cloud Security

---

# 📌 Final Summary

A secure PHP weather dashboard application implementing authentication hardening, secure session handling, protected API communication, SQL injection prevention, XSS mitigation, and environment-based secret management.
