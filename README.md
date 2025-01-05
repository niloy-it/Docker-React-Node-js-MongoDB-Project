# Mobile Shop

This project is a full-stack web application designed to manage a Mobile Shop. It includes:

- A **Frontend** built with React for a dynamic user interface.
- A **Backend** built with Node.js and Express for API handling.
- A **MongoDB** database for data storage.

The frontend is served efficiently using **NGINX**, ensuring optimal performance and static file handling.

## Project Overview

This project allows users to explore mobile products, add them to a cart, and manage their purchases.
Developers can deploy this project seamlessly using Docker and Docker Compose.

![Mobile Shop Application](https://github.com/abrahimcse/Docker-PlayGround/blob/main/screenshots/mobile_shop.jpg)

---

## Features

- **Frontend**: React-based dynamic interface for user interaction.
- **Backend**: RESTful APIs for managing data.
- **Database**: MongoDB for efficient and scalable data storage.
- **Containerization**: Docker ensures consistent deployment across environments.

## Prerequisites

Ensure you have the following installed on your system:

- **Docker**: [Install Docker](https://docs.docker.com/get-docker/)
- **Docker Compose**: [Install Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

### 1. Cloning the Repository

Start by cloning the project repository:

```bash
git clone https://github.com/badhan-saha-bjit/mobile-shop.git
```

### 2. Navigating the Project

Navigate to the project directory:

```bash
cd mobile-shop/
```

Inside this directory, you'll find two main folders:

- **frontend/**: Contains the React frontend code.
- **backend/**: Contains the Node.js backend code.

### 3. Configuring the Frontend

To connect the frontend to the backend:

1. Navigate to the frontend directory:

   ```bash
   cd frontend/
   ```
2. Open the `.env` file to configure the API URL. Replace `<localhost>` with the IP address or hostname of your backend:

   ```bash
   vim .env
   ```

   Example `.env` file content:
   ```env
   # Development environment variables
   API_URL=http://<localhost>:5000/api
   ```
3. Save and exit the file.
4. Return to the root directory:

   ```bash
   cd ..
   ```

### 4. Directory Setup for Data Persistence

To persist MongoDB data on your host machine:

1. Create a directory for MongoDB data:
   ```bash
   mkdir -p /mobileshop/db
   ```
2. Grant read, write, and execute permissions:
   ```bash
   chmod 777 -Rf /mobileshop/db
   ```

### 5. Running the Project with Docker Compose

To build and start all project services:

1. Ensure you're in the root directory:

   ```bash
   cd /path/to/mobile-shop
   ```
2. Build and start the services:

   ```bash
   docker compose up -d
   ```

   This command will:

   - Build Docker images for the frontend and backend.
   - Start the containers for the frontend, backend, and MongoDB.
3. Verify that all services are running:

   ```bash
   docker ps
   ```

### 6. Accessing the Application

- **Frontend**: [http://localhost:3001](http://localhost:3001)
- **Backend**: API endpoints are available at [http://localhost:5000](http://localhost:5000)
- **Database**: MongoDB is accessible on `localhost:27017`.

## Stopping the Project

To stop all running containers:

```bash
docker compose down
```

This will remove the containers but keep the data in `/mobileshop/db`.

---

## Contributions

Feel free to fork this repository, submit issues, or create pull requests for improvements.

Enjoy working with the **Mobile Shop** project! 🚀
