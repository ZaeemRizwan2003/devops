pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub_zaeemrizwan23')
    }
    stages {
        stage('Build') {
            steps {
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                bat 'echo "Test is running"'
            }
        }
        stage('Docker build') {
            steps {
                bat 'docker build -t zaeemrizwan23/jenkins-integration:latest .'
            }
        }
        stage('Login') {
            steps {
                script {
                    def dockerUsername = env.DOCKERHUB_CREDENTIALS_USR
                    def dockerPassword = env.DOCKERHUB_CREDENTIALS_PSW
                    echo "Logging in to Docker Hub with user: ${dockerUsername}"
                    bat "echo ${dockerPassword} | docker login -u ${dockerUsername} --password-stdin"
                }
            }
        }
        stage('Push') {
            steps {
                bat 'docker push zaeemrizwan23/jenkins-integration:latest'
            }
        }
        stage('Deploy') {
            steps {
                bat 'echo "Deploying the application"'
            }
        }
    }
}
