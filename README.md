# Spring Boot CI/CD Pipeline with GitHub Actions, Docker & AWS EC2

A practical DevOps project that automates the build, containerization, and deployment of a Spring Boot application using GitHub Actions, Docker, Docker Hub, and AWS EC2.

## Project Overview

This project demonstrates how application code can move from GitHub to a running application on AWS EC2 through an automated CI/CD pipeline.

Whenever code is pushed to the main branch, GitHub Actions automatically starts the workflow.

## CI/CD Pipeline

Developer
   |
   | git push
   v
GitHub Repository
   |
   v
GitHub Actions
   |
   +--> Checkout Source Code
   |
   +--> Setup Java
   |
   +--> Maven Build
   |
   +--> Build Docker Image
   |
   +--> Push Image to Docker Hub
   |
   +--> Deploy to AWS EC2
   |
   v
Spring Boot Application

## Technologies Used

- Java
- Spring Boot
- Maven
- Git
- GitHub
- GitHub Actions
- Docker
- Docker Hub
- AWS EC2
- Linux

## Architecture

GitHub Repository
        |
        v
GitHub Actions
        |
   +----+----+
   |         |
   v         v
Maven     Docker
Build      Build
              |
              v
          Docker Hub
              |
              v
           AWS EC2
              |
              v
    Spring Boot Application

## GitHub Actions

The CI/CD workflow is located at:

.github/workflows/main.yml

The workflow runs automatically when changes are pushed to the main branch.

### Workflow Steps

1. Checkout source code
2. Set up Java
3. Build the Spring Boot application using Maven
4. Create the Docker image
5. Push the Docker image to Docker Hub
6. Deploy the application to AWS EC2
7. Run the Spring Boot application

## Docker

Docker is used to package the Spring Boot application into a container image.

Spring Boot Application
        |
        v
    Maven Build
        |
        v
        JAR
        |
        v
   Docker Image
        |
        v
    Docker Hub

## AWS EC2 Deployment

AWS EC2 is used as the deployment server.

The Docker image is pulled from Docker Hub and the containerized Spring Boot application is started on the EC2 instance.

Docker Hub
    |
    | Pull Image
    v
AWS EC2
    |
    | Run Container
    v
Spring Boot Application

## CI/CD Result

The GitHub Actions workflow was successfully executed and completed the automated build and deployment process.

The pipeline demonstrated:

- Automated source code checkout
- Java environment setup
- Maven build
- Docker image creation
- Docker image push
- AWS EC2 deployment
- Running Spring Boot application

The workflow successfully completed in approximately 1 minute 14 seconds.

## Project Structure

ci-cd-first/
|
├── .github/
│   └── workflows/
│       └── main.yml
|
├── src/
│   ├── main/
│   └── test/
|
├── Dockerfile
├── pom.xml
├── mvnw
├── mvnw.cmd
└── README.md

## Run Locally

Clone the repository:

git clone https://github.com/divyansh-cloudops/ci-cd-first.git

cd ci-cd-first

Build the application on Windows:

mvnw.cmd clean package

Build the application on Linux/macOS:

./mvnw clean package

Run the application:

java -jar target/*.jar

## Run with Docker

Build the Docker image:

docker build -t spring-boot-ci-cd .

Run the Docker container:

docker run -d -p 8080:8080 spring-boot-ci-cd

Check running containers:

docker ps

The application can be accessed on:

http://localhost:8080

## Trigger the CI/CD Pipeline

Make a code change and run:

git add .
git commit -m "Update application"
git push origin main

The push automatically triggers the GitHub Actions workflow.

## Key Learning

This project provided hands-on experience with:

- CI/CD fundamentals
- GitHub Actions workflows
- Maven build automation
- Docker containerization
- Docker Hub
- AWS EC2 deployment
- Linux server environment
- Git and GitHub
- Automated deployment workflows
- CI/CD troubleshooting

## Future Improvements

- Add automated unit testing
- Add Docker image versioning
- Use AWS ECR
- Provision infrastructure using Terraform
- Add deployment health checks
- Add rollback strategy
- Add monitoring and logging
- Deploy using Kubernetes
- Improve production secrets management

## Project Highlights

Git Push
   |
   v
GitHub
   |
   v
GitHub Actions
   |
   v
Maven
   |
   v
Docker
   |
   v
Docker Hub
   |
   v
AWS EC2
   |
   v
Running Spring Boot Application

## Repository

GitHub:
https://github.com/divyansh-cloudops/ci-cd-first

## Author

Divyansh Saini

B.Tech Computer Science Engineering
Cloud & DevOps Enthusiast

GitHub:
https://github.com/divyansh-cloudops

---

This project was created for hands-on learning and practical understanding of CI/CD, Docker, GitHub Actions, and AWS cloud deployment.
