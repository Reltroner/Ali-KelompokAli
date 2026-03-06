# Depok City Drinking Water Information System

### Municipal Water Service Management Platform

A modular **Node.js + Express backend system** designed to manage **user authentication, service forms, and citizen submissions** for municipal drinking water services in Depok City.

The system demonstrates practical backend engineering concepts including:

* REST-style API routing
* JWT-based authentication
* modular MVC architecture
* relational database modeling
* file upload handling
* middleware-based security

This platform can serve as a **foundation for municipal service portals, citizen reporting systems, or internal government workflow tools**.

---

# System Context

Municipal water service departments typically receive reports and service requests from citizens regarding:

* water supply issues
* service complaints
* infrastructure reports
* service requests

This system digitizes the process by providing a centralized backend service that enables:

* citizen authentication
* digital form submissions
* service request tracking
* administrative dashboards
* document/file uploads

---

# Key Features

### Authentication System

Secure user authentication using **JWT-based session management**.

Capabilities:

* user registration
* login authentication
* token validation
* protected API routes

---

### Citizen Form Submission

Users can submit service requests through structured forms.

Example use cases:

* water supply complaints
* infrastructure damage reports
* service requests

Each submission is stored and tracked in the database.

---

### File Upload Support

Users can upload supporting files such as:

* photos
* documents
* evidence of service issues

Uploaded files are stored in:

```
assets/files_upload/
```

---

### User Management

Administrative capabilities include:

* managing user accounts
* retrieving user profiles
* managing citizen submissions

---

# System Architecture

The application follows a **layered MVC-inspired architecture**.

```
Client / Browser
        │
        ▼
     Express Router
        │
        ▼
   Controller Layer
        │
        ▼
     Model Layer
        │
        ▼
   MySQL Database
```

### Architectural Principles

The system is designed with the following principles:

**Separation of concerns**

Each layer is responsible for a specific concern:

| Layer       | Responsibility           |
| ----------- | ------------------------ |
| Routes      | API endpoint definitions |
| Controllers | business logic           |
| Models      | database interaction     |
| Middleware  | security & validation    |
| Views       | static UI templates      |

**Modularity**

Controllers and routes are separated to ensure maintainability.

**Extensibility**

The architecture supports future additions such as:

* service approval workflows
* notification systems
* analytics dashboards

---

# Project Structure

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

# Data Flow

Typical request lifecycle.

```
User Request
      │
      ▼
Express Route
      │
      ▼
Controller Logic
      │
      ▼
Model Query
      │
      ▼
Database Response
      │
      ▼
JSON Response to Client
```

---

# Database

The system uses **MySQL** as the primary datastore.

Schema file:

```
database/gpt-team/gpt-team.sql
```

Core entities:

| Table       | Description              |
| ----------- | ------------------------ |
| users       | system users             |
| forms       | form definitions         |
| submissions | citizen form submissions |

Example relationship:

```
User
  │
  ▼
Form Submission
  │
  ▼
Uploaded Files
```

---

# Security Model

Security is implemented using **JWT authentication**.

Middleware responsible:

```
middleware/verifyToken.js
```

Security responsibilities:

* validate JWT tokens
* block unauthorized requests
* protect sensitive endpoints
* enforce session integrity

Authentication flow:

```
User Login
   │
   ▼
JWT Token Generated
   │
   ▼
Client Stores Token
   │
   ▼
Token Sent in Request Header
   │
   ▼
verifyToken Middleware
   │
   ▼
Authorized API Access
```

---

# API Overview

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

# Installation

Clone repository:

```bash
git clone https://github.com/yourusername/gpt-team.git
cd gpt-team
```

Install dependencies:

```bash
npm install
```

Create environment configuration:

```
.env
```

Example configuration:

```
PORT=3000

DB_HOST=localhost
DB_USER=root
DB_PASSWORD=
DB_NAME=gpt_team

JWT_SECRET=your_secret_key
```

---

# Running the Application

Start the server:

```
npm start
```

Development mode:

```
npm run dev
```

Application available at:

```
http://localhost:3000
```

---

# Engineering Concepts Demonstrated

This repository demonstrates several backend engineering practices:

* modular route design
* controller separation
* JWT-based authentication
* middleware-based security
* relational database modeling
* file upload handling
* REST-style API architecture

---

# Future Improvements

Potential architectural enhancements include:

* Role-Based Access Control (RBAC)
* OpenAPI API documentation
* request validation layer
* service layer abstraction
* notification system
* microservice architecture

---

# Contributors

Based on repository history:

* **Raidan Sandra (Reltroner)**
* **Ali161725**

---

# Project Purpose

This project demonstrates how to design a **structured backend service using Node.js and Express** with authentication, routing, and relational database integration.

It serves as a **learning platform for backend system architecture and API design**.

---

# License

Open source project for educational and development purposes.
