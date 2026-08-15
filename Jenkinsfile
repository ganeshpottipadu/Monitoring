pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Verify Project') {
            steps {
                sh '''
                    echo "Project files:"
                    ls -la

                    echo "Docker version:"
                    docker --version
                '''
            }
        }

        stage('Docker Check') {
            steps {
                sh '''
                    echo "Running Docker containers:"
                    docker ps
                '''
            }
        }

        stage('Docker Build') {
            steps {
                sh '''
                    echo "Building Docker image..."
                    docker build -t monitoring-app:latest .
                '''
            }
        }

        stage('Docker Deploy') {
            steps {
                sh '''
                    echo "Stopping old container..."
                    docker stop monitoring-app || true

                    echo "Removing old container..."
                    docker rm monitoring-app || true

                    echo "Starting new container..."
                    docker run -d --name monitoring-app -p 8082:80 monitoring-app:latest

                    echo "Deployment completed!"
                '''
            }
        }
    }

    post {
        success {
            echo 'CI/CD pipeline completed successfully!'
        }

        failure {
            echo 'CI/CD pipeline failed!'
        }
    }
}
