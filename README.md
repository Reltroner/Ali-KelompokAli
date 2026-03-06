A simple **Node.js + Express web application** designed to manage users, forms, and submissions with authentication and dashboard interface.

This project demonstrates a typical **MVC-style backend structure** with routing, controllers, middleware, and database integration.

---

# 📦 Tech Stack

* **Node.js**
* **Express.js**
* **MySQL**
* **JWT Authentication**
* **HTML / CSS (Static Views)**

---

# 📂 Project Structure

```
.
├── app.js
├── bin/
│   └── www
├── controllers/
│   ├── authController.js
│   ├── formsController.js
│   ├── homeController.js
│   ├── submissionController.js
│   └── usersController.js
├── database/
│   └── gpt-team.sql
├── middleware/
│   └── verifyToken.js
├── models/
│   ├── forms.js
│   ├── submissions.js
│   └── users.js
├── routes/
│   ├── auth.js
│   ├── forms.js
│   ├── submission.js
│   ├── users.js
│   └── index.js
├── public/
│   ├── index.html
│   └── stylesheets/
│       └── style.css
├── views/
│   ├── Dashboard.html
│   ├── Login.html
│   ├── Profil.html
│   ├── Kontak.html
│   ├── Matkul.html
│   ├── class.html
│   └── class-details.html
├── assets/
│   ├── avatar/
│   └── files_upload/
├── package.json
└── README.md
```

---

# ⚙️ Features

### 🔐 Authentication

* User login system
* JWT token verification
* Protected routes using middleware

### 👤 User Management

* Create and manage user profiles
* User-related endpoints

### 📄 Forms Management

* Create and manage forms
* Store form submissions

### 📥 Submission Handling

* Upload files
* Store and process submission data

### 📊 Dashboard

* Basic dashboard interface
* Navigation across application modules

---

# 🗄 Database

Database schema is provided in:

```
database/gpt-team/gpt-team.sql
```

To import the database:

```sql
CREATE DATABASE gpt_team;
USE gpt_team;

SOURCE gpt-team.sql;
```

---

# 🚀 Installation

Clone the repository:

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

Example:

```
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=
DB_NAME=gpt_team
JWT_SECRET=your_secret_key
```

Run the application:

```bash
npm start
```

Or using nodemon:

```bash
npm run dev
```

---

# 🌐 Application Access

After running the server:

```
http://localhost:3000
```

---

# 🧠 Architecture Overview

The application follows a simplified **MVC architecture**:

```
Routes
   ↓
Controllers
   ↓
Models
   ↓
Database
```

Middleware is used for:

* Authentication
* Token verification
* Request validation

---

# 👥 Contributors

GitHub contributors based on repository history:

* **Raidan Sandra (Reltroner)**
* **Ali161725**

---

# 📜 License

This project is provided for educational and development purposes.
