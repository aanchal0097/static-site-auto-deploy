pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t static-site .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop static-container || true'
                sh 'docker rm static-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8000:80 --name static-container static-site'
            }
        }
    }
}
