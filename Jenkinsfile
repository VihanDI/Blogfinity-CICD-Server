pipeline {
    agent any

    stages {
        stage('Stop already running backend') {
            steps {  
                sh 'docker stop blogfinity-backend-container'
            }
        }

        stage('Remove old container') {
            steps {  
                sh 'docker rm blogfinity-backend-container'
            }
        }

        stage('Remove old Docker Image') {
            steps {  
                sh 'docker rmi inupavihan/blogfinity-backend'
            }
        }

        stage('Clear builder cache') {
            steps {  
                sh 'docker builder prune -f'
            }
        }

        stage('Build Docker Image') {
            steps {  
                sh 'docker build -t inupavihan/blogfinity-backend .'
            }
        }

        stage('Run Docker Image') {
            steps {  
                sh 'docker run -d -p 3000:8081 --name blogfinity-backend-container inupavihan/blogfinity-backend'
            }
        }
    }
}