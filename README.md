# User Authentication and Authorization with Bearer Token

## Overview
This project implements user authentication and authorization using Bearer tokens in a Node.js application. The application follows the MVC (Model-View-Controller) pattern and integrates MongoDB using Mongoose for data storage. It uses JWT (JSON Web Tokens) for secure user sessions and includes detailed API documentation.

---

## Features
- **User Registration**: Allows users to create an account with a username, email, and password. Passwords are securely hashed before storage.
- **User Login**: Authenticates users by verifying credentials and returns a JWT for session management.
- **Protected Routes**: Uses middleware to verify JWT tokens and provides access to authorized routes.
- **API Documentation**: Comprehensive Postman documentation with sample requests and responses.
- **Error Handling**: Provides meaningful error messages and validations for robust API functionality.

---

## Tech Stack
- **Backend**: Node.js, Express.js
- **Database**: MongoDB (with Mongoose ODM)
- **Authentication**: JWT (JSON Web Token)
- **Testing**: Postman

---

## Project Structure
```
/project-folder
├── /models 
│   └── user.js                 # Defines Mongoose schemas and models
├── /controllers
│   └── authController.js       # Contains controller logic for API endpoints
├── /middleware
│   └── authMiddleware.js       # Middleware for token validation
├── /routes
│   └── authRoutes.js           # Sets up API endpoints
├── /views
├── .env
├── app.js                      # Entry point of the application
├── package.json
└── README.md

```

---

## Installation
1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   ```

3. **Configure Environment Variables**:
   - Create a `.env` file in the project root.
   - Add the following variables:
     ```
     MONGO_URI=<your-mongodb-connection-string>
     JWT_SECRET=<your-jwt-secret>
     PORT=5000
     ```

4. **Start the Server**:
   ```bash
   npm start
   ```
   The server will run on `http://localhost:5000`.

---

## API Endpoints

### **User Registration**
- **Method**: POST
- **URL**: `/api/auth/register`
- **Body**:
  ```json
  {
    "username": "testuser",
    "email": "testuser@example.com",
    "password": "securepassword"
  }
  ```
- **Response**:
  ```json
  {
    "message": "User registered successfully."
  }
  ```

### **User Login**
- **Method**: POST
- **URL**: `/api/auth/login`
- **Body**:
  ```json
  {
    "email": "testuser@example.com",
    "password": "securepassword"
  }
  ```
- **Response**:
  ```json
  {
    "token": "<your-jwt-token>"
  }
  ```

### **Get User Info**
- **Method**: GET
- **URL**: `/api/auth/me`
- **Headers**:
  ```
  Authorization: Bearer <your-jwt-token>
  ```
- **Response**:
  ```json
  {
    "_id": "user_id",
    "username": "testuser",
    "email": "testuser@example.com",
    "createdAt": "timestamp",
    "updatedAt": "timestamp"
  }
  ```

---

## Deployment
1. **Deploy on Render**:
   - Create a new service in [Render](https://render.com/).
   - Connect your GitHub repository.
   - Set up environment variables in Render.
   - Deploy the service.

2. **Submit URLs**:
   - Provide the API base URL and GitHub repository link as instructed.

---

## API Documentation
- Use Postman to test API endpoints.
- Include examples of requests and responses in the shared Postman collection.
- Replace sensitive data with placeholders before sharing publicly.

---

## Terms and Conditions
- Do not share confidential documents or sensitive information.
- Adhere to the open-source agreement but do not reference the company’s name.
- Your source code will not be used for commercial purposes.

---

Link to Postman Documentation
[Authentication and Authorization API Documentation](https://www.postman.com/vaibhavapriya/workspace/public/collection/40143357-2a7f25e1-9411-4c83-9931-595c4a43ed99?action=share&creator=40143357)

Link to Deployment
[Authentication and Authorization API](https://authentication-and-authorization-di6g.onrender.com)

---

