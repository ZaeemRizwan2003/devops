

pipeline {
   
    agent any
  environment{
     DOCKERHUB_CREDENTIALS=credentials('dockerhub_zaeemrizwan23')
  }
    stages{
        stage('Build'){
            steps{
                bat 'npm install'

            }
        }
        stage('test'){
            steps{pipeline {
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
                    echo "Logging in to Docker Hub with user: ${env.DOCKERHUB_CREDENTIALS_USR}"
                    bat 'echo %DOCKERHUB_CREDENTIALS_PSW% | docker login -u %DOCKERHUB_CREDENTIALS_USR% --password-stdin'
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

                bat 'echo "Test is running"'
            }
        }
        stage('Docker build'){
            steps{
                bat 'docker build -t zaeemrizwan23/jenkins-integration:latest .'
            }
        }
       stage('login') {
    steps {
        script {
            echo "Username: ${env.DOCKERHUB_CREDENTIALS_USR}"
            echo "Password: ${env.DOCKERHUB_CREDENTIALS_PSW}"
        }
        bat 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
    }
}

        stage('push'){
            steps{
                bat 'docker push zaeemrizwan23/jenkins-integration:latest'
            }
        }
        stage('deploy'){
            steps{
                bat 'echo "Deploying the application"'
            }
        } 
    }
}
