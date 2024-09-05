pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Add build commands here
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Add test commands here
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
                // Add code analysis commands here
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Add security scan commands here
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                // Add deployment commands here
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Add integration test commands here
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                // Add production deployment commands here
            }
        }
    }

    post {
        always {
            emailext(
                subject: "Jenkins Pipeline Notification",
                body: "Build ${env.BUILD_ID} has finished.",
                to: "mail2sainathreddy123@gmail.com"
            )
        }
    }
}
