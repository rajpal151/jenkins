pipeline {
    agent any

    environment {
        DIRECTORY_PATH = "sample.html"
        TESTING_ENVIRONMENT = "test env"
        PRODUCTION_ENVIRONMENT = "prod env"
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetching source code from ${DIRECTORY_PATH}"
                echo "Compiling the code and generating artifacts"
            }
        }

        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Checking the quality of the code"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application to ${TESTING_ENVIRONMENT}"
            }
        }

        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep(time: 10, unit: 'SECONDS')
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to ${PRODUCTION_ENVIRONMENT} production environment"
            }
        }
    }
}
