pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'  // Replace with your build command, e.g., 'npm run build' for Node.js
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                sh 'run_unit_tests_command'  // Replace with your test command
                sh 'run_integration_tests_command'  // Replace with your integration test command
            }
        }

        stage('Code Analysis') {
            steps {
                sh 'sonar-scanner'  // Example: SonarQube scanner
            }
        }

        stage('Security Scan') {
            steps {
                sh 'owasp-zap-scan-command'  // Replace with your security scan command
            }
        }

        stage('Deploy to Staging') {
            steps {
                sh 'deploy-to-staging-command'  // Replace with your staging deployment command
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                sh 'run_integration_tests_on_staging_command'  // Replace with your staging integration tests command
            }
        }

        stage('Deploy to Production') {
            steps {
                sh 'deploy-to-production-command'  // Replace with your production deployment command
            }
        }

        // Archive HTML Artifact
        stage('Archive HTML Artifact') {
            steps {
                archiveArtifacts artifacts: 'sample.html', allowEmptyArchive: true
            }
        }
    }

    post {
        success {
            emailext body: 'Testing Email from Jenkins', subject: 'Emaill Testing', to: 'replyme151@gmail.com'
            }
        }
    }
}
