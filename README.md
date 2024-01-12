# Challenge

## Overview

This repository contains a simple web application with two main components:

1. **API**: Written in Laravel PHP, the API serves as the backend for the application and listens on port 8000.
2. **Client**: Developed using Nuxt.js, the client is the frontend of the application and listens on port 3000.

### Environment Variables

- **API Directory**: Take a look at the `.env` file in the API directory. It should contain the necessary credentials to connect to the database.

  ```env
    DB_CONNECTION=mysql
    DB_HOST=db
    DB_PORT=3306
    DB_DATABASE=bookapi
    DB_USERNAME=app
    DB_PASSWORD=password
  ```

- **Client Directory**: Check the `.env` file in the Client directory. It should contain the connection string to connect to the API.


 step-by-step instructions on how to run the application using Docker Compose.

The db service uses the official MySQL image, sets up environment variables for the database configuration, exposes port 3306, and creates a volume for persistent data storage.

The api service uses the official PHP-FPM image, sets the working directory to the Laravel API directory, and mounts the local ./api directory into the container.

The client service uses the official Node.js image, sets the working directory to the Nuxt.js client directory, and mounts the local ./client directory into the container.

The nginx service uses the official Nginx image, exposes port 80, and mounts the local ./nginx/conf.d directory into the container for Nginx configuration

  ```env
    VITE_API_URL=http://api:8000
  ```
