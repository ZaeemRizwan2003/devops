pipeline {
    agent any

    stages {
        stage('Build'){
            steps{
                bat 'npm install'
            }
        }
        stage('Test'){
            steps{
                bat 'echo "Test is running"'
            }
        }
        stage('Deploy'){
            steps{
                bat 'echo "Deploying the application"'
            }
        }
    }
}
