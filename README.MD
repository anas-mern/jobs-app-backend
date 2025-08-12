# 🔐 Jobs API (with Authentication)

This is the **backend** for the Task Manager project. It includes a full **REST API** built with **Node.js**, **Express**, **MongoDB**, and features **JWT-based authentication**. Users can register, login, and manage the job opportunities securely.

---

## 🚀 Technologies Used

- Node.js
- Express.js
- MongoDB & Mongoose
- JWT (jsonwebtoken)
- bcryptjs
- dotenv
- CORS
- Morgan

---

## 📁 Project Structure

```
Backend/
│
├── connections/       # DB connection and env setup
├── controllers/       # Logic for auth and task operations
├── models/            # User & Task mongoose models
├── routes/            # Express route handlers
├── middlewares/       # Auth middleware (protect routes)
├── .env               # Environment variables
├── app.js             # Express app config
├── server.js          # Entry point
└── README.md          # You're here!
```

---

## ⚙️ Setup Instructions

1. **Install dependencies**

```bash
npm install
```

2. **Create a `.env` file**

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
```

3. **Run the server**

```bash
npm run dev
```

Server runs on `http://localhost:5000`

---

## 🔐 Authentication Endpoints

| Method | Endpoint           | Description         |
| ------ | ------------------ | ------------------- |
| POST   | /api/auth/register | Register a new user |
| POST   | /api/auth/login    | Login and get token |

---

## ✅ Task Endpoints (Protected)

All routes below require a **valid JWT token** in the `Authorization` header as `Bearer <token>`.

| Method | Endpoint      | Description       |
| ------ | ------------- | ----------------- |
| GET    | /api/jobs     | Get user jobs     |
| POST   | /api/jobs     | Create new task   |
| GET    | /api/jobs/:id | Get task by ID    |
| PUT    | /api/jobs/:id | Update task by ID |
| DELETE | /api/jobs/:id | Delete task by ID |

---

## 🧪 Example Task Object

```json
{
  "company": "IBM",
  "position": "MERN Stack",
  "status": "interview",
  "createdBy": "objectID()"
}
```

---

## 🔒 Example Auth Flow

1. **Register** a new user
2. Receive JWT token after login
3. Send token in headers to access jobs:

```http
Authorization: Bearer your_jwt_token
```

---
