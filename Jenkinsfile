pipeline {
    agent none
    stages {
        stage('Checkout Source') {
            steps {
                checkout scm
            }
        }      
        stage('Build') {
            steps {
                sh 'docker build .'
            }
        }
    }
}
