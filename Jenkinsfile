pipeline {
    agent any

    tools {
        maven 'Maven 3.x'  // Replace 'Maven 3.x' with the name you used for Maven installation in Jenkins
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
                bat 'mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                bat 'mvn test'
                // Add your integration test commands here
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
                // Replace this with the actual code analysis tool you are using
                bat 'mvn sonar:sonar'  // Example using SonarQube for code analysis
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Replace this with the actual security scan tool you are using
                bat 'mvn verify -DskipTests'  // Example command, adjust according to your security scan tool
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                // Add your deployment script or command for staging environment
                bat 'deploy-staging.bat'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Add your integration test commands for the staging environment
                bat 'integration-tests-staging.bat'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                // Add your deployment script or command for production environment
                bat 'deploy-production.bat'
            }
        }
    }

    post {
        always {
            emailext(
                subject: "Jenkins Pipeline Notification - Build ${env.BUILD_ID}",
                body: """\
Build ${env.BUILD_ID} has finished.
Status: ${currentBuild.currentResult}
Logs are attached.
""",
                to: "mail2sainathreddy123@gmail.com",
                attachmentsPattern: '**/build.log'  // Adjust the log file path if needed
            )
        }
    }
}
