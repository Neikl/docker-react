pipeline {
    agent any
    stages {
        stage('Checkout Source') {
            steps {
                checkout scm
            }
        }      
        stage('Docker Build') {
            steps {
                sh "docker build -t neikl/frontend:latest ."
            }
        }
        stage('Docker Run') {
            steps {
                sh "docker run -p 8090:80 neikl/frontend:latest"
            }
        }        
    }
}
