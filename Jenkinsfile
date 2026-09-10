pipeline {
    agent any

    triggers {
        // Poll GitHub every 5 minutes; H spreads load so all jobs don't fire at once
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Task: Compile the source code and package it into a deployable artifact (JAR/WAR).'
                echo 'Tool: Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Task: Run unit tests to verify individual methods, then integration tests to verify components work together.'
                echo 'Tool: JUnit for unit tests, Selenium for end-to-end integration tests'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Task: Statically analyse the code for bugs, code smells and maintainability issues against industry standards.'
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Task: Scan source code and third-party dependencies for known vulnerabilities (CVEs).'
                echo 'Tool: OWASP Dependency-Check'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Task: Deploy the packaged artifact to a staging server that mirrors production.'
                echo 'Tool: AWS EC2 (deployment automated with Ansible)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Task: Run the integration test suite against the staging deployment to confirm it behaves correctly in a production-like environment.'
                echo 'Tool: Postman with Newman CLI'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Task: Promote the verified build to the production server and make it live for users.'
                echo 'Tool: AWS EC2 (deployment automated with Ansible)'
            }
        }
    }
}
