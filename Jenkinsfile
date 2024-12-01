pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository
                checkout scm
            }
        }
        stage('Verify Files') {
            steps {
                // Check if the required files are present
                script {
                    if (!fileExists('index.html') || !fileExists('style.css')) {
                        error("Required files 'index.html' or 'style.css' are missing!")
                    } else {
                        echo "Files 'index.html' and 'style.css' found in the repository."
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                // Example: Copy files to a deployment directory
                sh '''
                echo "Deploying files..."
                mkdir -p /path/to/deploy/directory
                cp index.html /path/to/deploy/directory/
                cp style.css /path/to/deploy/directory/
                echo "Deployment complete."
                '''
            }
        }
    }
}
