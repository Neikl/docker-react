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
                sh "echo test"
            }
        }
    }
}
