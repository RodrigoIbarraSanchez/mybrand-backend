# Contact Form API

This is a RESTful API backend service designed to manage contact form submissions. It provides endpoints for creating, reading, updating, and deleting contact form entries, making it perfect for integration with dashboard applications that need to manage contact form data.

## Features

- CRUD operations for contact form submissions
- MongoDB database integration
- RESTful API architecture
- CORS enabled
- Environment-based configuration

## Prerequisites

- Node.js (v12 or higher)
- MongoDB (local instance or MongoDB Atlas)
- npm or yarn package manager

## Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file based on `.env.template`:
   ```
   PORT=3000
   MONGODB_URI=your_mongodb_connection_string
   ```

## Running the Application

### Development mode:
```bash
npm run dev
```

### Production mode:
```bash
npm start
```

## API Endpoints

### Get All Contacts
- **URL:** `/api/contacts`
- **Method:** `GET`
- **Success Response:**
  ```json
  [
    {
      "_id": "contact_id",
      "name": "John Doe",
      "email": "john@example.com",
      "message": "Hello there!",
      "createdAt": "2023-08-20T12:00:00.000Z"
    }
  ]
  ```

### Get Single Contact
- **URL:** `/api/contacts/:id`
- **Method:** `GET`
- **Success Response:**
  ```json
  {
    "_id": "contact_id",
    "name": "John Doe",
    "email": "john@example.com",
    "message": "Hello there!",
    "createdAt": "2023-08-20T12:00:00.000Z"
  }
  ```

### Create Contact
- **URL:** `/api/contacts`
- **Method:** `POST`
- **Request Body:**
  ```json
  {
    "name": "John Doe",
    "email": "john@example.com",
    "message": "Hello there!"
  }
  ```
- **Success Response:**
  ```json
  {
    "_id": "contact_id",
    "name": "John Doe",
    "email": "john@example.com",
    "message": "Hello there!",
    "createdAt": "2023-08-20T12:00:00.000Z"
  }
  ```

### Update Contact
- **URL:** `/api/contacts/:id`
- **Method:** `PUT`
- **Request Body:**
  ```json
  {
    "name": "John Doe Updated",
    "email": "john.updated@example.com",
    "message": "Updated message"
  }
  ```
- **Success Response:**
  ```json
  {
    "_id": "contact_id",
    "name": "John Doe Updated",
    "email": "john.updated@example.com",
    "message": "Updated message",
    "createdAt": "2023-08-20T12:00:00.000Z"
  }
  ```

### Delete Contact
- **URL:** `/api/contacts/:id`
- **Method:** `DELETE`
- **Success Response:**
  ```json
  {
    "message": "Contact deleted successfully"
  }
  ```

## Error Responses

All endpoints may return the following error responses:

- **404 Not Found:**
  ```json
  {
    "message": "Contact not found"
  }
  ```

- **400 Bad Request:**
  ```json
  {
    "message": "Error message describing the issue"
  }
  ```

- **500 Server Error:**
  ```json
  {
    "message": "Something went wrong!"
  }
  ```

## Environment Variables

| Variable | Description | Default |
|----------|-------------|----------|
| PORT | Port number for the server | 3000 |
| MONGODB_URI | MongoDB connection string | mongodb://localhost:27017/contact-form |

## License

This project is licensed under the MIT License.