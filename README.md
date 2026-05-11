# RBAC Authentication Service

A secure Role-Based Access Control (RBAC) authentication service built with Node.js, Express, and PostgreSQL.

This project allows employees within an organization to securely log in and access projects based on their assigned roles and permissions.

---

# Features

* User Registration
* Secure Login Authentication
* JWT-Based Authentication
* Role-Based Access Control (RBAC)
* Protected API Routes
* Project Access Management
* Forgot Password via Email Verification
* Password Hashing with bcrypt
* CI/CD with GitHub Actions
* PostgreSQL Database Integration

---

# Tech Stack

## Backend

* Node.js
* Express.js

## Database

* PostgreSQL

## Authentication

* JSON Web Tokens (JWT)
* bcrypt

## Email Service

* NodeMailer

## Testing

* Jest
* SuperTest

## CI/CD

* GitHub Actions

---

# Project Architecture

```text
Frontend
   ↓
Express API
   ↓
Authentication Middleware
   ↓
PostgreSQL Database
```

---

# Authentication Flow

```text
User Login
    ↓
Verify Password
    ↓
Generate JWT
    ↓
Return Token
    ↓
Frontend Stores Token
    ↓
Protected Requests Use Bearer Token
```

---

# RBAC Flow

```text
User
  ↓
Assigned Role
  ↓
Role Contains Permissions
  ↓
Protected Route Checks Permission
```

---

# Database Schema

## Users

```sql
users
- id
- email
- password_hash
- role
- created_at
```

## Projects

```sql
projects
- id
- name
- description
```

## Project Access

```sql
project_access
- user_id
- project_id
```

## Password Reset Codes

```sql
password_reset_codes
- id
- user_id
- code
- expires_at
```

---

# API Endpoints

## Authentication

### Register User

```http
POST /auth/register
```

### Login User

```http
POST /auth/login
```

### Forgot Password

```http
POST /auth/forgot-password
```

### Reset Password

```http
POST /auth/reset-password
```

---

# Protected Routes

### Get Projects

```http
GET /projects
```

### Create Project (Admin Only)

```http
POST /projects
```

---

# Environment Variables

Create a `.env` file in the root directory.

```env
PORT=5000

DATABASE_URL=your_database_url

JWT_SECRET=your_super_secret_key

EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_email_app_password
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/your-username/rbac-auth-service.git
```

## Install Dependencies

```bash
npm install
```

## Start Development Server

```bash
npm run dev
```

---

# Running Tests

```bash
npm test
```

---

# CI/CD Pipeline

GitHub Actions automatically:

* Installs dependencies
* Runs tests
* Verifies builds
* Prepares deployment

Workflow file:

```text
.github/workflows/backend.yml
```

---

# Security Features

* Password hashing using bcrypt
* JWT expiration handling
* Protected routes using middleware
* Role-based authorization
* Email verification for password resets
* Environment variable protection
* HTTP authorization headers

---

# Future Improvements

* Refresh Tokens
* Multi-Factor Authentication (MFA)
* Organization/Tenant Support
* Audit Logging
* OAuth/OIDC Integration
* Docker Support
* Session Revocation
* Fine-Grained Permissions

---

# Learning Objectives

This project was built to learn:

* Authentication systems
* JWT handling
* RBAC authorization
* Backend API development
* PostgreSQL relationships
* CI/CD pipelines
* Secure password handling
* Email verification systems

---

# Contributors

* Your Name
* Team Members

---

# License

This project is licensed under the MIT License.
