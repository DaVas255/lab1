pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh '/usr/local/bin/docker build -t lab1-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '/usr/local/bin/docker rm -f lab1-container || true'
                sh '/usr/local/bin/docker run -d -p 3000:3000 --name lab1-container lab1-app'
            }
        }
    }
}