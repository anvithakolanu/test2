pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/anvithakolanu/pythonExample.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                script {
                    // Install pytest directly
                    bat 'pip install pytest'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Run the tests using pytest
                    bat 'prime.py'
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add your deployment commands here
            }
        }
    }
}
