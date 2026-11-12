pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code'
            }
        }

        stage('Build and Test') {
            steps {
                echo 'Building and testing the application'
                bat 'mvn clean verify'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                echo 'Deploying application to Kubernetes'
            }
        }
    }
}