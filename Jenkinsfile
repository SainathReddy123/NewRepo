pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                // Add build steps here
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Add test steps here
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
                // Add code analysis steps here
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Add security scan steps here
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                // Add deployment steps here
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Add integration test steps here
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                // Add production deployment steps here
            }
        }
    }

    post {
        always {
            // Send email notification with log file
            emailext(
                subject: "Jenkins Pipeline Build - ${currentBuild.currentResult}",
                body: """
                The build has completed with the result: ${currentBuild.currentResult}.
                
                Please find the build logs attached.
                """,
                attachmentsPattern: '**/log/*.log',
                to: 'mail2sainathreddy123@gmail.com'
            )
        }
    }
}
