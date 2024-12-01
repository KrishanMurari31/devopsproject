pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Building..."'
                // Add build commands, e.g., `npm install` or `mvn clean install`
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
                // Add testing commands, e.g., `npm test` or `mvn test`
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying..."'
                // Add deployment commands
            }
        }
    }
}
