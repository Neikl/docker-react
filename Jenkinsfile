node {
    def app
    stage('Clone Repository') {
        git branch: "master", url: "https://github.com/Neikl/docker-react.git"
    }
    stage('Docker Build') {
        sh "docker build -t 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest ."
    }
    stage('Push Image to ECR') {
        docker.withRegistry('https://922079431449.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:react-ecr-role') {
            sh "docker push 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest"
        }
    }
    stage('Pull Image from ECR') {
        docker.withRegistry('https://922079431449.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:react-ecr-role') {
            sh "docker pull 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest"
        }
    }	
    stage('Deploy on EB') {
        docker.withRegistry('https://922079431449.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:react-ecr-role') {        
            sh "eb deploy"
        }
    }	
}
