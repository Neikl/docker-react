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
                echo "docker build -t neikl/frontend:B${BUILD_NUMBER} -f Dockerfile ."
            }
        }
    }
}
