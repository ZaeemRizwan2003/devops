pipeline {
    agent any
    environment{
        DOCKERHUB_CREDENTIALS=credentials('dockerhub_zaeemrizwan23')
    }

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
        stage('Docker build'){
            steps{
                bat 'docker build -t zaeemrizwan23/jenkins-integration:latest'
            }
        }
        stage('login'){
            steps{
                bat 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stddin'
            }
        }
        stage('login'){
            steps{
                bat 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('push'){
            steps{
                bat 'docker push zaeemrizwan23/jenkins-integration:latest'
            }
        }
        stage('Deploy'){
            steps{
                bat 'echo "Deploying the application"'
            }
        }
    }
}