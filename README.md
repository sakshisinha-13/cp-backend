# CodePlayground – Backend

This is the backend for the CodePlayground project, built using Node.js, Express.js, and MongoDB. It handles APIs for retrieving coding problems, code submissions, test case evaluations, and user authentication.

---

## Features

- RESTful APIs for coding problems
- Dynamic code execution and test case evaluation
- MongoDB integration for persistent storage
- Clean structure for scalability and maintenance
- CORS-enabled for frontend integration

---

## Tech Stack

- Node.js
- Express.js
- MongoDB with Mongoose
- dotenv for environment config
- child_process for dynamic code execution
- CORS, body-parser, etc.

---

## Folder Structure

cp-backend/
├── routes/ # Route definitions for problems, execution, etc.
├── controllers/ # Logic for handling requests
├── models/ # Mongoose models (if using DB)
├── utils/ # Utility functions (code runner, test checker)
├── server.js # Entry point of the app
├── .env # Environment variables
├── package.json # Dependencies and scripts

---

## Getting Started

```bash
git clone https://github.com/sakshisinha-13/cp-backend.git
cd cp-backend

# Install dependencies
npm install

# Set up .env
touch .env
# Add variables like:
# PORT=5000
# MONGO_URI=mongodb+srv://..

# Start the server
npm start
Server runs on http://localhost:5000

API Endpoints
GET /api/problems – Fetch all problems
POST /api/execute – Execute submitted code against test cases
POST /api/submit – Submit code (optional persistence)
GET /api/problem/:id – Fetch specific problem by ID

