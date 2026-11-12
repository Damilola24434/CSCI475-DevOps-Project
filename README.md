

\# CSCI 475 DevOps Course Project



\## Project Overview

This project demonstrates an automated CI/CD pipeline using Jenkins, Docker, and Kubernetes. It uses a Java Spring Boot web application as the sample application.



\## Application

The application displays the following message when accessed:



CSCI 475 DevOps Pipeline is running successfully!



\## Technologies

\- Java 21

\- Spring Boot

\- Maven

\- Git and GitHub

\- Jenkins

\- Docker

\- Kubernetes



\## Build and Test

Build and verify the application using Maven:



```bash

mvn clean verify

```



This command compiles the application and runs its tests.



\## Docker

Build the Docker image:



```bash

docker build -t devops-demo:1.0 .

```



Run the container:



```bash

docker run -d --name devops-demo-container -p 8081:8080 devops-demo:1.0

```



Access the application at http://localhost:8081.



\## Project Structure

\- `src/` - Java application source code and tests.

\- `pom.xml` - Maven project configuration and dependencies.

\- `Dockerfile` - Instructions for building the Docker image.

\- `.dockerignore` - Files excluded from the Docker build context.

\- `Jenkinsfile` - Jenkins pipeline definition.

\- `k8s/deployment.yaml` - Kubernetes Deployment configuration.

\- `k8s/service.yaml` - Kubernetes Service configuration.



