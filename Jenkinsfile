pipeline {
    agent {
        docker {
            image 'node:18-alpine'
        }
    }
    environment {
        DOCKER_HOST = 'tcp://docker:2375'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building the Node.js application...'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    def dockerImage = docker.build("my-node-app:${env.BUILD_NUMBER}")
                    echo "Docker image built: ${dockerImage}"
                }
            }
        }
    }
}

