pipeline {
    agent any
    environment {
        IMAGE_NAME = "dawrinmiller/django_project"
    }
    stages{
        stage('Checkout'){
            steps{
                git branch 'main', url: 'https://github.com/dawrinmiller/django_project'
            }
        }
        stage('Build Docker image'){
            steps{
                bat "docker build -t %IMAGE_NAME%:latest ."
            }
        }
        stage('Push to Dockerhub'){
            steps{
                withCredentials([usernamePassword])
            }
        }
    }
}
