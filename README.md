Dockerized Nginx Web App Deployment
This project demonstrates how to containerize a simple Nginx web application using Docker, create a custom Docker image, and deploy it to AWS Elastic Beanstalk.

Table of Contents
Project Overview

Features

Prerequisites

Project Structure

Getting Started

Building the Custom Docker Image

Running the Custom Docker Image Locally

Deployment to AWS Elastic Beanstalk

Custom index.html

Project Overview
This project focuses on the practical application of Docker for packaging and deploying a web application. It involves:

Understanding Docker containers and images.

Running a standard Nginx Docker image.

Creating a custom Docker image that serves a personalized index.html file.

Deploying this custom Docker image to AWS Elastic Beanstalk, showcasing cloud deployment capabilities.

Features
Custom Nginx web server image.

Serves a personalized "Hello from Rushabh's custom Docker image!" page.

Demonstrates local Docker build and run commands.

Highlights deployment using AWS Elastic Beanstalk.

Prerequisites
Before you begin, ensure you have the following installed:

Docker Desktop

An AWS account (if you plan to deploy to Elastic Beanstalk)

AWS CLI (optional, for Elastic Beanstalk deployment)

Project Structure
The core files for this project would typically include:

.
├── Dockerfile
└── index.html

Dockerfile: Contains instructions for Docker to build the custom Nginx image.

index.html: The custom web page content to be served by Nginx.

Getting Started
Building the Custom Docker Image
To build your custom Docker image, navigate to the root directory of your project (where your Dockerfile and index.html are located) in your terminal and run the following command:

docker build -t my-custom-nginx-app .

-t my-custom-nginx-app: Tags the image with the name my-custom-nginx-app. You can choose any name you prefer.

.: Indicates that the Dockerfile is in the current directory.

Running the Custom Docker Image Locally
After building the image, you can run it locally to test your custom web page.

docker run -d -p 80:80 my-custom-nginx-app

-d: Runs the container in detached mode (in the background).

-p 80:80: Maps port 80 on your host machine to port 80 inside the container. This allows you to access the web server via http://localhost.

my-custom-nginx-app: The name of the custom image you built.

If you encounter an error about port 80 already being in use, it means another process is using that port. You might need to stop the conflicting process or use a different host port (e.g., -p 8080:80). To stop a running container, you can use docker ps to find its ID and then docker stop <container_id>.

Once running, open your web browser and navigate to http://localhost. You should see the "Hello from Rushabh's custom Docker image!" message.

Deployment to AWS Elastic Beanstalk
The project was also deployed to AWS Elastic Beanstalk, a service that simplifies the deployment of applications on AWS. Elastic Beanstalk abstracts away much of the underlying infrastructure setup.

The deployment process typically involves:

Creating an Elastic Beanstalk application and environment.

Uploading your Dockerfile and index.html (and potentially a Dockerrun.aws.json if using multi-container Docker or specific configurations).

Elastic Beanstalk then builds and deploys your Docker image to the defined environment.

Upon successful deployment, you would access your application via the provided Elastic Beanstalk URL (e.g., rushabhapp-env.eba-u9cekbii.us-west...).

Custom index.html
The index.html file included in this project contains the following content:

<!DOCTYPE html>
<html>
<head>
    <title>My Custom Docker Page</title>
</head>
<body>
    <h1>Hello from Rushabh's custom Docker image!</h1>
</body>
</html>
