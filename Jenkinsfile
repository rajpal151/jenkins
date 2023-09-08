pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "mvn clean install"  // Replace with your build command, e.g., 'npm run build' for Node.js
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "run_unit_tests_command"  // Replace with your test command
                echo "run_integration_tests_command"  // Replace with your integration test command
            }
        }

        stage('Code Analysis') {
            steps {
                echo "sonar-scanner"  // Example: SonarQube scanner
            }
        }

        stage('Security Scan') {
            steps {
               echo "owasp-zap-scan-command"  // Replace with your security scan command
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "deploy-to-staging-command"  // Replace with your staging deployment command
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "run_integration_tests_on_staging_command"  // Replace with your staging integration tests command
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "deploy-to-production-command"  // Replace with your production deployment command
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
            emailext subject: 'Email Testing',
                      body: 'Testing Email from Jenkins',
                      mimeType: 'text/html',
                      to: 'replyme151@gmail.com',
                      attachmentsPattern: 'sample.html'
            }
        }
    }
