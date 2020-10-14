node('docker') {

    stage 'Checkout'
        checkout scm
    stage 'Build & UnitTest'
        sh "docker build -t neikl/frontend:B${BUILD_NUMBER} -f Dockerfile ."
}
