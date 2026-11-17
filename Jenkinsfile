
pipeline {
    agent any

    environment {
        IMAGE_NAME = 'cloudops-dashboard'
        IMAGE_TAG = 'v1'
    }

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Fetching source code from GitHub...'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t cloudops-dashboard:v1 -f dockerfile .'
            }
        }

        stage('Load Image into Minikube') {
            steps {
                echo 'Loading Docker image into Minikube...'
                sh 'minikube image load cloudops-dashboard:v1'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                echo 'Deploying application to Kubernetes...'
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }

        stage('Verify Deployment') {
            steps {
                echo 'Checking Kubernetes deployment...'
                sh 'kubectl rollout status deployment/cloudops-deployment'
                sh 'kubectl get pods'
                sh 'kubectl get services'
            }
        }
    }

    post {
        success {
            echo 'CLOUDOPS PROJECT DEPLOYED SUCCESSFULLY!'
        }

        failure {
            echo 'Pipeline failed. Check Jenkins Console Output.'
        }

        always {
            echo 'CI/CD Pipeline execution completed.'
        }
    }
}
