pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Description: Build the code using a build automation tool.
                                echo 'Building the code using Maven...'
                // Example command: mvn clean package
                bat 'mvn clean package'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                // Description: Run unit tests to ensure the code functions as expected
                // and integration tests to ensure the components work together.
                              echo 'Running unit and integration tests...'
                // Example command: mvn test
                bat 'mvn test'
                bat 'mvn verify'
            }
        }

        stage('Code Analysis') {
            steps {
                // Description: Integrate a code analysis tool to analyze the code for industry standards.
                                echo 'Performing code analysis with SonarQube...'
                // Example command: sonar-scanner
                bat 'sonar-scanner'
            }
        }

        stage('Security Scan') {
            steps {
                // Description: Perform a security scan on the code to identify vulnerabilities.
               
                echo 'Performing security scan...'
                // Example command: dependency-check --project "Project Name" --out dependency-check-report.html
                bat 'dependency-check --project "Project Name" --out dependency-check-report.html'
            }
        }

        stage('Deploy to Staging') {
            steps {
                // Description: Deploy the application to a staging server.
                                echo 'Deploying to staging server...'
                // Example command: aws deploy create-deployment --application-name my-app --s3-location bucket=my-bucket,key=my-app.zip
                bat 'aws deploy create-deployment --application-name my-app --s3-location bucket=my-bucket,key=my-app.zip'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                // Description: Run integration tests on the staging environment.
                                echo 'Running integration tests on staging...'
                // Example command: run-integration-tests.sh
                bat 'run-integration-tests.sh'
            }
        }

        stage('Deploy to Production') {
            steps {
                // Description: Deploy the application to a production server.
               
                echo 'Deploying to production server...'
                // Example command: aws deploy create-deployment --application-name my-app --s3-location bucket=my-bucket,key=my-app.zip
                bat 'aws deploy create-deployment --application-name my-app --s3-location bucket=my-bucket,key=my-app.zip'
            }
        }
    }

    post {
        always {
            emailext(
                subject: "Jenkins Pipeline Notification",
                body: "Build ${env.BUILD_ID} has finished.\nStage: ${currentBuild.currentResult}\nLogs attached.",
                to: "mail2sainathreddy123@gmail.com",
                attachmentsPattern: '**/build.log'
            )
        }
    }
}
