# Stayfinder — Dockerized Web Application

Stayfinder is a Node.js web application built with Express, EJS, and MongoDB Atlas. This repository contains the application source code and Docker configuration needed to run it in a container.

## Tech Stack

- Node.js
- Express.js
- EJS
- MongoDB Atlas
- Docker

## Prerequisites

- Docker Desktop (Windows/macOS) or Docker Engine (Linux)
- A MongoDB Atlas connection string
- Required environment variables for the application

## Run with Docker

### 1. Clone the repository

```bash
git clone YOUR_NEW_REPOSITORY_URL
cd YOUR_REPOSITORY_FOLDER
```

Replace the placeholders with your new GitHub repository URL and folder name.

### 2. Configure environment variables

Create a `.env` file in the project root. Add the environment variables required by the application, including your MongoDB Atlas connection string.

**Never commit your real `.env` file or publish credentials.**

### 3. Build the Docker image

```bash
docker build -t stayfinder:latest .
```

### 4. Run the container

```bash
docker run --name stayfinder-container -p 8080:8080 --env-file .env stayfinder:latest
```

Open [http://localhost:8080](http://localhost:8080) in your browser.

### 5. Stop the container

Press `Ctrl + C` if running in the foreground. If running in detached mode, use:

```bash
docker stop stayfinder-container
```

## Docker Configuration

- `Dockerfile` — defines how the application image is built.
- `.dockerignore` — excludes unnecessary files and secrets from the build context.
- `.gitignore` — prevents local dependencies and environment files from being committed.

## Notes

- The application connects to MongoDB Atlas, so a separate MongoDB container is not required.
- Ensure your MongoDB Atlas network access settings permit connections from the environment where the application runs.
- This repository is intended to demonstrate containerization of a Node.js web application.

## License

Add a license if you intend to distribute this project under specific open-source terms.