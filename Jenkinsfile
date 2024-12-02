pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Verify Files') {
            steps {
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
                bat '''
                echo Deploying files...
                if not exist "C:\\deploy" mkdir C:\\deploy
                copy index.html C:\\deploy\\
                copy style.css C:\\deploy\\
                echo Deployment complete.
                '''
            }
        }
    }
}