pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Specify your build tool here, e.g., Maven
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running tests...'
                // Specify test tools, e.g., JUnit, TestNG
            }
            post {
                success {
                    archiveArtifacts artifacts: '*.log', allowEmptyArchive: true
                    emailext to: 'adeeltask6c@gmail.com',
                         subject: "Test Success: Jenkins Pipeline",
                         body: "The unit and integration tests completed successfully.",
                         from: 'adeeltask6c@gmail.com',
                         attachLog: true
                }
                failure {
                    archiveArtifacts artifacts: '*.log', allowEmptyArchive: true
                    emailext to: 'adeeltask6c@gmail.com',
                         subject: "Test Failed: Jenkins Pipeline",
                         body: "The unit and integration tests failed. Please check the logs.",
                         from: 'adeeltask6c@gmail.com',
                         attachLog: true
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code...'
                // Specify code analysis tool, e.g., SonarQube
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for security vulnerabilities...'
                // Specify security tool, e.g., OWASP Dependency Check
            }
            post {
                success {
                    archiveArtifacts artifacts: '*.log', allowEmptyArchive: true
                    emailext to: 'adeeltask6c@gmail.com',
                         subject: "Security Scan Success: Jenkins Pipeline",
                         body: "The security scan completed successfully.",
                         from: 'adeeltask6c@gmail.com',
                         attachLog: true
                }
                failure {
                    archiveArtifacts artifacts: '*.log', allowEmptyArchive: true
                    emailext to: 'adeeltask6c@gmail.com',
                         subject: "Security Scan Failed: Jenkins Pipeline",
                         body: "The security scan failed. Please check the logs.",
                         from: 'adeeltask6c@gmail.com',
                         attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                // Deploy to staging server, e.g., AWS EC2
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Test in staging environment
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                // Deploy to production server, e.g., AWS EC2
            }
        }
    }
}
