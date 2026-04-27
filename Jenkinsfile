pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t static-site .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker stop static-container || exit 0'
                bat 'docker rm static-container || exit 0'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 8000:80 --name static-container static-site'
            }
        }
    }
}