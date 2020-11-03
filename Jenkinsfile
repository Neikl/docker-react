node {
    def app
    stage('Clone Repository') {
        git branch: "master", url: "https://github.com/Neikl/docker-react.git"
    }
    /*stage('Docker Build') {
        sh "docker build -t 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest ."
    }
    stage('Push Image to ECR') {
        docker.withRegistry('https://922079431449.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:react-ecr-role') {
            sh "docker push 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest"
        }
    }*/
    stage('Creating Infrastructure') {
        sh "cd ./01-infrastructure && terraform init"
        //sh "cd ./01-infrastructure && terraform apply -var-file='production.tfvars' -auto-approve"
        sh "cd ./01-infrastructure && terraform destroy -var-file='production.tfvars' -auto-approve"
    }
    stage('Creating Platform') {
        sh "cd ./02-platform && terraform init"
        //sh "cd ./02-platform && terraform apply -var-file='production.tfvars' -auto-approve"
        sh "cd ./02-platform && terraform destroy -var-file='production.tfvars' -auto-approve"
    }    
    stage('Creating ECS Service') {
        sh "cd ./03-application && terraform init"
        //sh "cd ./03-application && terraform apply -var-file='production.tfvars' -auto-approve"
        sh "cd ./03-application && terraform destroy -var-file='production.tfvars' -auto-approve"
    }     
    
    /*stage('Pull Image from ECR') {
        docker.withRegistry('https://922079431449.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:react-ecr-role') {
            sh "docker pull 922079431449.dkr.ecr.us-east-1.amazonaws.com/react:latest"
        }
    }	
    stage('Deploy on EB') {       
        sh "eb deploy"
    }*/	
}
