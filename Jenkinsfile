pipeline {
    agent any 
    stages {
        stage('deploy pods') {
            steps {
                sh "kubectl apply -f deployment.yaml "
                sh "kubectl apply -f service.yaml" 
                sh "minikube service --url hostname-service"                
            }
        }
    }
}