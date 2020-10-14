pipeline {
    agent any
    stages {
        stage('Checkout Source') {
            steps {
                checkout scm
            }
        }      
        stage('Build') {
            steps {
                sh 'docker build -t neikl/frontend:latest .'
            }
        }
    }
}
