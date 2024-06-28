pipeline {
    agent any

    stages {
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