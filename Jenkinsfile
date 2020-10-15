node {
    def app
    stage('Clone repository') {
        git branch: "master", url: "https://github.com/Neikl/docker-react.git"
    }
    stage('Build image') {
        sh "docker build -t 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest ."
    }
    stage('Push image to ECR') {
        docker.withRegistry('https://922079431449.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:react-ecr-role') {
            sh "docker push 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest"
        }
    }
    stage('Pull image from ECR') {
        docker.withRegistry('https://922079431449.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:react-ecr-role') {
            sh "docker pull 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest"
        }
    }
    stage('Docker run') {
        docker.withRegistry('https://922079431449.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:react-ecr-role') {
            sh "docker run -d -p 8090:80 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest"
        }
    }	
}
