# USuggest — Dockerized Web Application 🐳

USuggest is a Node.js web application built with Express.js, EJS, and MongoDB Atlas. This repository demonstrates how to containerize the application with Docker and run it from a published Docker image.

## 🛠️ Tech Stack

- Node.js
- Express.js
- EJS
- MongoDB Atlas
- Docker

## 🐳 Docker Hub Image

The prebuilt image is available on Docker Hub:

**[Pull USuggest from Docker Hub](https://hub.docker.com/r/shayreen/usuggest)**

Image name: `shayreen/usuggest:latest`

## Prerequisites

- Docker Desktop on Windows or macOS, or Docker Engine on Linux
- A MongoDB Atlas connection string
- Your required Cloudinary credentials
- A session secret for the application

## 🚀 Run USuggest with Docker

### 1. Pull the image

Download the published image:

```bash
docker pull shayreen/usuggest:latest
```

### 2. Configure environment variables

Create a file named `.env` in your working directory and add your own valid credentials:

```dotenv
ATLAS_URL=your_mongodb_atlas_connection_string
SESSION_SECRET=your_session_secret
CLOUD_API_KEY=your_cloudinary_api_key
CLOUD_API_SECRET=your_cloudinary_api_secret
```

Replace these placeholders with your own values. Check the application source code for any additional required environment variables.

**Security:** Never commit your real `.env` file to GitHub or include credentials in a public image.

### 3. Run the container

Make sure port `8080` is available on your computer, then run:

```bash
docker run --name usuggest-container -p 8080:8080 --env-file .env shayreen/usuggest:latest
```

### 4. Open the application

Visit:

[http://localhost:8080](http://localhost:8080)

The application needs valid environment variables and access to the configured external services to work correctly.

### 5. Stop the container

If the container is running in the foreground, press `Ctrl + C`.

If it is running in detached mode, stop it with:

```bash
docker stop usuggest-container
```

### 6. Remove the container (optional)

After stopping it, remove the container with:

```bash
docker rm usuggest-container
```

Removing the container does not remove the published image from Docker Hub.

## 📂 Repository Structure

- `Dockerfile` — instructions for building the application image.
- `.dockerignore` — excludes unnecessary files from the Docker build context.
- `.gitignore` — excludes local dependencies and environment files from Git.
- `app.js` — application entry point.
- `routes/`, `models/`, `views/`, `public/` — application code and assets.

## 📝 Notes

- USuggest connects to MongoDB Atlas; a separate MongoDB container is not required.
- Configure MongoDB Atlas network access so the environment running the container can connect.
- Keep your credentials private and use your own environment variables.
- The image published on Docker Hub currently targets `linux/amd64`.

## 📄 License

No open-source license has been specified yet. Add a license only if you have the right to distribute the project under the chosen terms.