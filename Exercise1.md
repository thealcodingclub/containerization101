# Exercise 1: "Hello World" Web Application

This exercise introduces Docker containerization through the development of a simple "Hello World" web application.

## Prerequisites

- **Docker**: Make sure Docker is installed and running on your system. You can install Docker from [Docker's official site](https://docs.docker.com/get-docker/).
- **Docker Basics**: Familiarize yourself with Docker commands and container management.

## Step 1: Create the Application

1. Create a new directory for the project:
   ```bash
   mkdir hello-world-web
   cd hello-world-web
   ```

2. Inside the project directory, create a simple `index.html` file with the following content:
   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Hello World</title>
   </head>
   <body>
       <h1>Hello World from Docker!</h1>
   </body>
   </html>
   ```

## Step 2: Create the Dockerfile

In the same directory, create a `Dockerfile` to containerize the web application.

```Dockerfile
# Use an official Nginx image as the base
FROM nginx:latest

# Copy the HTML file to the default Nginx directory
COPY index.html /usr/share/nginx/html/index.html

# Expose port 80 for web traffic
EXPOSE 80
```

## Step 3: Build and Run the Docker Container

1. **Build the Docker image**:
   ```bash
   docker build -t hello-world-web .
   ```

2. **Run the Docker container**:
   ```bash
   docker run -p 8080:80 hello-world-web
   ```

3. **Test the application**: Open a browser and navigate to `http://localhost:8080`. You should see the "Hello World" message.

---

This `.md` file covers the steps to set up, containerize, and run the "Hello World" web application in Docker.
