pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'dosoba24434/devops-demo:1.0'
        KUBECONFIG = '/var/jenkins_home/kubeconfig'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code checked out'
            }
        }

        stage('Build and Test') {
            steps {
                sh 'mvn clean verify'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-credentials',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh 'echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin'
                    sh 'docker push $DOCKER_IMAGE'
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/deployment.yaml'
                sh 'kubectl apply -f k8s/service.yaml'
                sh 'kubectl rollout status deployment/devops-demo -n devops-demo'
                sh 'kubectl get pods -n devops-demo'
                sh 'kubectl get services -n devops-demo'
            }
        }
    }
}
