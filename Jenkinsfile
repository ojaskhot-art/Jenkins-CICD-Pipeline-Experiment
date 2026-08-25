pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling Java program...'
                bat 'javac Main.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing compiled program...'
                bat 'if exist Main.class (echo Test Passed: Main.class created successfully) else (echo Test Failed & exit /b 1)'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                bat 'java Main'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                bat 'echo Deployment successful!'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'CI/CD Pipeline failed!'
        }
    }
}