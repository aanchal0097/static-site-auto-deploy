pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/aanchal0097/static-site-auto-deploy.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t static-site .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 8000:80 static-site'
            }
        }
    }
}