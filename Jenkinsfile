pipeline {
    agent { dockerfile true }
    stages {
        stage('Checkout Source') {
            steps {
                checkout scm
            }
        }      
        stage('Build') {
            steps {
                sh 'docker build -t "neikl/frontend:latest" .'
            }
        }
    }
}
