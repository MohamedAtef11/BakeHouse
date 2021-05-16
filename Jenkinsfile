pipeline {
    agent any 
    stages {
        stage('deploy pods') {
            steps {
                sh "kubectl proxy --address 0.0.0.0 --accept-hosts '.*'"

                sh "kubectl apply -f deployment.yaml "
                sh "kubectl apply -f service.yaml" 
                sh "minikube service --url hostname-service"                
            }
        }
    }
}