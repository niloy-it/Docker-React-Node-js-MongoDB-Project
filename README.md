# mobile-shop

Project: Mobile Shop
This project consists of a Frontend built with React, a Backend built with Node.js, and a MongoDB database.

The frontend is served efficiently using NGINX, ensuring optimal performance and static file handling.


Prerequisites
Ensure you have the following installed on your system:

Docker: Install Docker
Docker Compose: Install Docker Compose
Directory Setup for Data Persistence
To persist MongoDB data on your host machine:

# Create a directory for MongoDB data(root_user)
mkdir -p /mobileshop/db

# Grant read, write, and execute permissions(root_user)
chmod 777 -Rf /mobileshop/db
Configuring Frontend to Connect to Backend
Navigate to the frontend directory:

cd frontend/
Open the .env file and update the API URL to point to the backend service. Replace <localhost> with the IP address or hostname of your backend:

vim .env
Example content of .env:

# Development env variables

API_URL=http://<localhost>:5000/api
Save and exit the file.

Running the Project with Docker Compose
To build and start all services (frontend, backend, and database):

Navigate to the project root directory where the docker-compose.yml file is located:

cd /path/to/Docker-PlayGround
Run the following command to build and start the services:

docker compose up -d --build
This command will:

Build Docker images for the frontend and backend.
Start the containers for frontend, backend, and MongoDB.
Verify that all containers are running:

docker compose ps
Accessing the Application
Frontend: Open your browser and navigate to http://localhost:3001.
Backend: API endpoints are accessible at http://localhost:5000.
Database: MongoDB runs on localhost:27017.
Stopping the Project
To stop all running containers:

docker compose down
This will also remove the containers but keep the persistent data in /mobileshop/db.

Enjoy running the Mobile Shop project!
