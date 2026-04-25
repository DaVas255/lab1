pipeline {
    agent any

    environment {
        PATH = "/usr/local/bin:/Applications/Docker.app/Contents/Resources/bin:${env.PATH}"
    }

    stages {
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