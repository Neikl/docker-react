node {
    def app
    stage('Clone repository') {
        git branch: "master", url: "https://github.com/Neikl/docker-react.git"
    }
    stage('Build image') {
        sh "docker build -t 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest ."
    }
    stage('Push image') {
        docker.withRegistry('https://922079431449.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:react-ecr-role') {
            sh "docker push 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest"
        }
    }
}
