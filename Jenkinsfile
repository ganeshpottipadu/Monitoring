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

    }

    post {
        success {
            echo 'CI pipeline completed successfully!'
        }

        failure {
            echo 'CI pipeline failed!'
        }
    }
}
