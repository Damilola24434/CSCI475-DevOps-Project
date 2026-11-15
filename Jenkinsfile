pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                sh 'git branch --show-current'
                sh 'ls -la'
            }
        }

        stage('Build and Test') {
            steps {
                echo 'Building and testing the application'
                sh 'mvn clean verify'
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
