pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }
        stage('Build image') {
            steps {
                docker build -t pokedex-go .
            }
        }
        stage('Run container from image') {
            steps {
                docker run --rm -it -p 5555:5555 pokedex-go:latest
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}