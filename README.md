# Contact Management API
A simple RESTful API for managing user accounts and their contacts, built with Node.js, Express.js, and MongoDB using Mongoose.

## Table of Contents
- [Description](#description)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Error Handling](#error-handling)
- [License](#license)

## Description
This API allows users to register, log in, and manage their contacts securely. It is built using Node.js, Express.js, and MongoDB with Mongoose for database modeling. Authentication is handled using JWT, and all endpoints (except user registration and login) require an access token.

## Features
- User registration
- User login with JWT authentication
- Fetch all contacts (for the logged-in user)
- Get a specific contact by ID
- Create a new contact
- Update contact details
- Delete a contact
- Secure access to private endpoints using JWT tokens

## Installation

### Prerequisites
Ensure you have the following installed on your system:
- **Node.js** (v14 or later)
- **MongoDB** (Local installation or use MongoDB Atlas)

### Steps to Run the Project Locally:
1. Clone the repository:
   ```sh
   git clone https://github.com/AminduBhashana/contact-manager-backend-api.git
   ```
2. Navigate to the project directory:
   ```sh
   cd contact-manager-backend-api
   ```
3. Install the dependencies:
   ```sh
   npm install
   ```
4. Create a `.env` file in the root directory and add the following:
   ```sh
   PORT=3000
   CONNECTION=your_mongodb_connection_string
   ACCESS_TOKEN_SECRET=your_secret_key
   ```
5. Start the server:
   ```sh
   npm start
   ```
6. The API should now be running at `http://localhost:3000`.

## Usage
You can interact with the API using tools like **Postman** or **cURL**. Ensure you include the JWT token in the `Authorization` header when accessing private endpoints.

## API Endpoints

### User Authentication
- **Register a new user** :: `POST /api/users/register`
- **Login user** :: `POST /api/users/login`
- **Get current user info** (requires token) :: `GET /api/users/current`

### Contact Management (Requires Authentication)
- **Get all contacts** :: `GET /api/contacts`
- **Get a specific contact by ID** :: `GET /api/contacts/:id`
- **Add a new contact** :: `POST /api/contacts`
- **Update a contact** :: `PUT /api/contacts/:id`
- **Delete a contact** :: `DELETE /api/contacts/:id`

## Error Handling
This API follows proper error-handling practices using HTTP status codes:
- `400 Bad Request` - Missing or invalid parameters
- `401 Unauthorized` - Invalid or missing authentication token
- `403 Forbidden` - User does not have permission to access the resource
- `404 Not Found` - Resource does not exist
- `500 Internal Server Error` - Server-side issues

## License
This project is licensed under the MIT License.

