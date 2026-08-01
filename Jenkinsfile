pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t shopkart:latest .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop shopkart-web || true'
                sh 'docker rm shopkart-web || true'
            }
        }

        stage('Run New Container') {
            steps {
                 sh 'docker run -d --name shopkart-web -p 8088:80 shopkart:latest'
            }
        }

    }
}
