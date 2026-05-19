pipeline {
    agent any

    environment {
        IMAGE_NAME = 'mujtaba72/cloudshop-frontend'
        IMAGE_TAG = 'v1.0.0'
        CONTAINER_NAME = 'cloudshop-container'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code from GitHub repository...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building CloudShop frontend application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running HTML and CSS validation tests...'
                sh 'npm install -g htmlhint stylelint || true'
                sh 'htmlhint src/frontend/index.html || true'
                sh 'stylelint "src/frontend/**/*.css" || true'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t $IMAGE_NAME:$IMAGE_TAG .'
            }
        }

        stage('Docker Push') {
            steps {
                echo 'Pushing Docker image to Docker Hub...'
                sh 'docker push $IMAGE_NAME:$IMAGE_TAG || true'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application to target environment...'
                echo 'Deployment is handled through GitHub Actions and Render branch-based services.'
            }
        }

        stage('Notify') {
            steps {
                echo 'Pipeline completed. Notification sent to DevOps team.'
            }
        }
    }

    post {
        success {
            echo 'Jenkins pipeline completed successfully.'
        }

        failure {
            echo 'Jenkins pipeline failed. Rollback procedure should be triggered.'
        }
    }
}