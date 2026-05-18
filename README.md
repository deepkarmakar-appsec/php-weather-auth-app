# 🌦️ PHP Weather Auth App

> Secure PHP weather application with authentication, session security, server-side API proxying, and layered web security protections.

---

<!-- 📸 MAIN DASHBOARD BANNER HERE -->
<img width="1604" height="911" alt="login" src="https://github.com/user-attachments/assets/336f03f0-7dcd-47e7-9917-acfb9abad0a5" />


<img width="1594" height="907" alt="register" src="https://github.com/user-attachments/assets/9c5f54b8-9aed-479f-b89e-7e8d33df5943" />

<img width="1579" height="840" alt="dashboard" src="https://github.com/user-attachments/assets/075a16f3-5b02-4026-ba2a-7a5f0e47cce7" />

---

# 🌐 Overview

PHP Weather Auth App is a secure weather dashboard application built using PHP and MySQL.

The application includes:

- User authentication system
- Real-time weather dashboard
- Secure server-side weather API proxy
- Session security protections
- Secure routing and access control
- Environment-based secret management

---

# 🚀 Features

## 🔐 Authentication System

- User Registration
- Secure Login
- Logout Handling
- Session-based Authentication
- Protected Dashboard Routes

---

## 🌦️ Weather Dashboard

- Real-time weather data
- Secure backend API integration
- Server-side weather API proxy
- Dynamic city search
- Responsive dashboard interface

---

## 🔒 Security Features

✅ SQL Injection Protection  
✅ Password Hashing  
✅ Session Fixation Prevention  
✅ CSRF Protection  
✅ Account Lockout Protection  
✅ Secure Session Cookies  
✅ XSS Protection  
✅ DOM-based XSS Prevention  
✅ Environment-based Secret Management  
✅ Protected Routes  

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

# 🌦️ Weather API Security Flow

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

## 🔐 SQL Injection Protection

Uses PDO prepared statements:

```php
$stmt = $con->prepare("SELECT * FROM users WHERE email = ?");
```

### Benefit

User input never directly joins SQL queries.

---

## 🔒 Password Hashing

Passwords secured using:

```php
password_hash()
password_verify()
```

### Benefit

Passwords never stored in plain text.

---

## 🔑 Session Security

Secure session handling using:

```php
session_regenerate_id(true)
```

### Prevents

- Session fixation
- Session hijacking

---

## 🛡️ CSRF Protection

CSRF tokens validated on sensitive actions.

```php
hash_equals($_SESSION['csrf_token'], $_POST['csrf_token'])
```

### Benefit

Prevents unauthorized requests.

---

## 🚫 Account Lockout Protection

```text
Multiple failed login attempts
↓
Temporary account lock
```

### Prevents

- Brute-force attacks
- Credential stuffing

---

## 🔒 Secure Session Cookies

```text
HttpOnly
SameSite
Secure
```

### Benefits

- Prevents JavaScript cookie theft
- Reduces CSRF risk
- HTTPS-only cookie transmission

---

## 🛡️ XSS Protection

Output escaping using:

```php
htmlspecialchars()
```

### Prevents

- Reflected XSS
- Stored XSS

---

## 🔥 DOM-based XSS Prevention

Safe DOM updates used instead of:

```javascript
innerHTML
```

### Benefit

Prevents client-side script injection.

---

## 🔐 Environment Security

Sensitive secrets stored using:

```text
.env
```

### Includes

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

```text
HTML5
CSS3
JavaScript
PHP
MySQL
XAMPP
OpenWeather API
```

---

# 🌐 API Integration

## Weather API

Uses:

```text
OpenWeather API
```

## Security Design

- API key hidden from frontend
- Requests handled server-side
- Input validation applied
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
git clone YOUR_REPOSITORY_URL
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

Import MySQL database into XAMPP/phpMyAdmin.

---

## Start Server

```text
Apache + MySQL via XAMPP
```

---

# 🔥 Example Security Flow

```text
User Registers
↓
Password Hashed
↓
Secure Session Created
↓
User Logs In
↓
CSRF Validation
↓
Dashboard Access
↓
Weather Request Through API Proxy
↓
Secure Response Returned
```

---

# 🧠 Security Concepts Implemented

```text
Authentication
Authorization
CSRF Protection
Session Security
SQL Injection Prevention
XSS Protection
API Proxy Security
Environment Security
Brute-force Protection
Secure Cookies
```

---

# 🤝 Contribution

Pull requests are welcome.

Feel free to improve:
- Security
- Performance
- UI/UX
- API integrations

---

# 💡 Author

## Deep Karmakar

Security-focused Developer  
DevSecOps + Cloud Security Enthusiast

---

# 🔥 Final Summary

A secure PHP weather application implementing authentication hardening, session security, API proxy protection, SQL injection prevention, XSS defenses, and secure environment-based configuration.

---

# 🚀 Final One Line

A secure PHP weather dashboard application built with layered authentication, session protection, API security, and modern web security practices.
