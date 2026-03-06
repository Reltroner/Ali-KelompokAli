# Depok City Drinking Water Information System

A modular **Node.js + Express backend system** designed to manage **user authentication, forms, and submissions** with a structured MVC architecture and JWT-based access control.

This project demonstrates practical backend engineering concepts including:

* API routing
* Authentication middleware
* Modular controller architecture
* Database modeling
* File upload handling
* Protected routes using JWT

The system can serve as a **foundation for form management systems, LMS tools, or internal workflow platforms**.

---

# 🚀 System Overview

The application is structured as a lightweight backend service that exposes API endpoints and serves static views for interaction.

Core capabilities include:

* User authentication and token-based session management
* Form creation and management
* Submission storage
* File uploads
* Dashboard navigation
* Modular routing system

---

# 🧠 Architecture

The project follows a **layered MVC-inspired architecture**.

```
Client / Browser
        │
        ▼
     Routes
        │
        ▼
   Controllers
        │
        ▼
     Models
        │
        ▼
    Database
```

### Responsibilities

| Layer       | Responsibility                |
| ----------- | ----------------------------- |
| Routes      | Define API endpoints          |
| Controllers | Handle request logic          |
| Models      | Interact with database        |
| Middleware  | Security & request validation |
| Views       | Static UI pages               |

---

# 📂 Project Structure

```
.
├── app.js
├── bin/
│   └── www
│
├── controllers/
│   ├── authController.js
│   ├── formsController.js
│   ├── homeController.js
│   ├── submissionController.js
│   └── usersController.js
│
├── middleware/
│   └── verifyToken.js
│
├── models/
│   ├── forms.js
│   ├── submissions.js
│   └── users.js
│
├── routes/
│   ├── auth.js
│   ├── forms.js
│   ├── submission.js
│   ├── users.js
│   └── index.js
│
├── views/
│   ├── Dashboard.html
│   ├── Login.html
│   ├── Profil.html
│   ├── Kontak.html
│   ├── Matkul.html
│   ├── class.html
│   └── class-details.html
│
├── public/
│   ├── index.html
│   └── stylesheets/
│       └── style.css
│
├── assets/
│   ├── avatar/
│   └── files_upload/
│
├── database/
│   └── gpt-team.sql
│
├── package.json
└── README.md
```

---

# ⚙️ Core Features

## Authentication System

* User login endpoint
* JWT-based session token
* Token verification middleware
* Protected routes

Security flow:

```
User Login
   │
   ▼
JWT Token Issued
   │
   ▼
Token Stored Client Side
   │
   ▼
verifyToken Middleware
   │
   ▼
Protected API Access
```

---

## Forms Management

Allows creation and management of form data.

Typical workflow:

```
Admin creates form
      │
      ▼
Users submit responses
      │
      ▼
Submissions stored in database
```

Key components:

* formsController
* forms model
* forms routes

---

## Submission Handling

Handles user responses and uploaded files.

Capabilities:

* store submissions
* attach uploaded files
* map submission to forms

Upload files stored in:

```
assets/files_upload/
```

---

## User Management

Provides endpoints for:

* user creation
* profile retrieval
* account management

Controllers involved:

```
usersController.js
```

Model:

```
models/users.js
```

---

# 🗄 Database

The system uses **MySQL**.

Schema file provided in:

```
database/gpt-team/gpt-team.sql
```

Basic data entities:

| Table       | Purpose        |
| ----------- | -------------- |
| users       | account data   |
| forms       | form metadata  |
| submissions | form responses |

---

# 🔐 Security Layer

Authentication uses **JWT (JSON Web Token)**.

Middleware:

```
middleware/verifyToken.js
```

Responsibilities:

* validate JWT
* block unauthorized requests
* protect sensitive endpoints

---

# 📡 API Design

Example endpoint structure.

### Authentication

```
POST /auth/login
POST /auth/register
```

---

### Users

```
GET /users
GET /users/:id
POST /users
```

---

### Forms

```
GET /forms
POST /forms
GET /forms/:id
```

---

### Submissions

```
POST /submission
GET /submission/:id
```

---

# 🚀 Installation

Clone repository

```bash
git clone https://github.com/yourusername/gpt-team.git
cd gpt-team
```

Install dependencies

```bash
npm install
```

Create environment file

```
.env
```

Example configuration

```
PORT=3000

DB_HOST=localhost
DB_USER=root
DB_PASSWORD=
DB_NAME=gpt_team

JWT_SECRET=your_secret_key
```

---

# ▶ Running the Application

Start server

```
npm start
```

Development mode

```
npm run dev
```

Application will run at:

```
http://localhost:3000
```

---

# 🧪 Development Notes

This repository demonstrates several backend engineering practices:

* modular route design
* controller separation
* middleware-based security
* MVC-style organization
* file upload handling
* relational data modeling

The architecture is intentionally simple but extensible, allowing future expansion such as:

* role based access control
* REST API documentation
* validation layers
* service layer abstraction
* microservice separation

---

# 👥 Contributors

Based on repository commit history:

* **Raidan Sandra (Reltroner)**
* **Ali161725**

---

# 📌 Project Purpose

This project is intended as a **backend architecture learning project** demonstrating how to structure a Node.js application with authentication, routing, and database interaction.

---

# 📜 License

Open source project for educational and development purposes.
