# BlogApp Backend

Simple Blog Backend application built using Node.js, Express, and MongoDB. It supports creating posts, adding comments, and liking/unliking posts. 

## Folder Structure

```
/blogapp-backend
├── config
│   └── database.js
├── controllers
│   ├── commentController.js
│   ├── likeController.js
│   └── postController.js
├── models
│   ├── commentModel.js
│   ├── likeModel.js
│   └── postModel.js
├── routes
│   └── blog.js
├── .env
├── package.json
├── package-lock.json
└── index.js

```

## Getting Started

### Prerequisites

Make sure you have Node.js and MongoDB installed on your machine.

### Installation

1. Clone the repository

   ```bash
   git clone https://github.com/ravikant-diwakar/blogApp-backend
   ```

2. Navigate to the project directory

   ```bash
   cd blog-backend-app
   ```

3. Install the dependencies

   ```bash
   npm install
   ```

4. Create a `.env` file in the root directory and add the following:

   ```
   PORT = 3000
   DATABASE_URL = mongodb://127.0.0.1:27017/blogAppDatabase
   ```

5. Start the MongoDB server if it's not already running.

### Running the App

1. Start the server

   ```bash
   npm start
   ```

2. The app will run at `http://localhost:3000`.

### API Endpoints

- **Default Route**

  ```http
  GET /
  ```

  - Response: HomePage

- **Create Post**

  ```http
  POST /api/v1/posts/create
  ```

  - Request Body:

    ```json
    {
      "title": "Post Title",
      "body": "Post Body"
    }
    ```

  - Response: Created Post Object

- **Get All Posts**

  ```http
  GET /api/v1/posts
  ```

  - Response: Array of all posts with likes and comments populated

- **Create Comment**

  ```http
  POST /api/v1/comments/create
  ```

  - Request Body:

    ```json
    {
      "post": "Post ID",
      "user": "User Name",
      "body": "Comment Body"
    }
    ```

  - Response: Updated Post Object with the new comment

- **Like Post**

  ```http
  POST /api/v1/likes/like
  ```

  - Request Body:

    ```json
    {
      "post": "Post ID",
      "user": "User Name"
    }
    ```

  - Response: Updated Post Object with the new like

- **Unlike Post**

  ```http
  POST /api/v1/likes/unlike
  ```

  - Request Body:

    ```json
    {
      "post": "Post ID",
      "like": "Like ID"
    }
    ```

  - Response: Updated Post Object without the unliked like

## Project Structure Explanation

- **config/database.js**: Contains the database connection logic.
- **controllers/**: Contains the controllers for handling requests related to comments, likes, and posts.
- **models/**: Contains the Mongoose schemas for comments, likes, and posts.
- **routes/blog.js**: Contains the routes for the API endpoints.
- **index.js**: The main entry point of the application.

