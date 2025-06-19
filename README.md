# CodePlayground Backend

This is the backend service for the **CodePlayground** platform. It powers the frontend by providing APIs to:

- Fetch coding problems from a MongoDB database
- Execute submitted C++ code
- Return test case results to the frontend

The backend is built using **Node.js**, **Express.js**, and **MongoDB**, with C++ code execution supported via the system’s `g++` compiler.

---

## Features

- RESTful API to retrieve problems and run code
- Executes user-submitted C++ code using `child_process`
- Validates code against test cases
- Connects to MongoDB Atlas for storing questions
- CORS support for integration with frontend (React)

---

## Tech Stack

- Node.js
- Express.js
- MongoDB Atlas
- Mongoose
- dotenv
- child_process (for executing C++ code)
- CORS middleware

---

## API Endpoints

### 1. Problem Routes

| Method | Endpoint               | Description                    |
|--------|------------------------|--------------------------------|
| GET    | `/api/problems`        | Fetch all coding problems      |
| GET    | `/api/problems/:id`    | Fetch a single problem by ID   |

### 2. Code Execution

| Method | Endpoint         | Description                        |
|--------|------------------|------------------------------------|
| POST   | `/api/execute`   | Executes C++ code with test cases  |

#### Example Request to `/api/execute`
```json
{
  "language": "c_cpp",
  "code": "#include<iostream>\nusing namespace std;\nint main() { int a,b; cin>>a>>b; cout<<a+b; return 0; }",
  "testCases": [
    { "input": "2 3", "expectedOutput": "5" },
    { "input": "4 6", "expectedOutput": "10" }
  ]
}

Getting Started
Prerequisites
Node.js and npm

g++ installed (required for C++ code execution)

A MongoDB Atlas database (or local MongoDB instance)

Installation
Clone the repository:

bash
Copy
Edit
git clone https://github.com/sakshisinha-13/cp-backend.git
cd cp-backend
Install dependencies:

bash
Copy
Edit
npm install
Set up environment variables:
Create a .env file in the root directory and add:

ini
Copy
Edit
MONGO_URI=your_mongodb_connection_string
PORT=5000
Start the server:

bash
Copy
Edit
node server.js
The backend should now be running at http://localhost:5000.

Folder Structure
bash
Copy
Edit
cp-backend/
├── models/
│   └── Problem.js           # Mongoose schema for coding problems
├── routes/
│   ├── execute.js           # Logic for compiling and executing C++ code
│   └── problemRoutes.js     # API routes to fetch problems
├── temp/                    # Temporary directory for compiled code
├── server.js                # Entry point and server setup
├── .env                     # Environment variables
