pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Divyansh2708/Docker.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run --rm myapp:latest'
            }
        }
    }
}
