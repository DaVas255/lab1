pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/DaVas255/lab1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t lab1-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f lab1-container || true'
                sh 'docker run -d -p 3000:3000 --name lab1-container lab1-app'
            }
        }
    }
}