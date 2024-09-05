 
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Add build commands here
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add test commands here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add deployment commands here
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
