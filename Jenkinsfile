pipeline {
    agent none
    stages {
        stage('Checkout Source') {
            checkout scm
        }        
        stage('Build') {
            steps {
                sh 'docker build .'
            }
        }
    }
}
