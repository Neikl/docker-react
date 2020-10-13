node('docker') {

    stage 'Checkout'
        checkout scm
    stage 'Build & UnitTest on Test Server'
        sh "docker-compose up --build"
    stage 'Build on Production Server'
        sh "docker build -t neikl/react_frontend:B${BUILD_NUMBER} -f Dockerfile ."
    stage 'Run App on Production Server'
        sh "docker run -it -p 8090:80 neikl/react_frontend:B${BUILD_NUMBER}"    
}
