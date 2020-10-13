node('docker') {

    stage 'Checkout'
        checkout scm
    stage 'Build & UnitTest on Test Server'
        sh "docker-compose up --build" 
}
