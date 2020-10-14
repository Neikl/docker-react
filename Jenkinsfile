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
                sh "docker build -t neikl/frontend:B${BUILD_NUMBER} ."
            }
        }
        stage('Docker Run') {
            steps {
                sh "docker run -d -p 8090:80 neikl/frontend:B${BUILD_NUMBER}"
            }
        }        
    }
}
