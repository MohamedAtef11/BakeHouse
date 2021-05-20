pipeline {
    agent any 
    stages {
        stage('deploy pods') {
            steps {
                withCredentials([file(credentialsId: 'kube.config', variable: 'kube')]) {

                sh "kubectl apply -f deployment.yaml  --kubeconfig $kube"
                sh "kubectl apply -f service.yaml  --kubeconfig $kube" 
                 }
            }
        }
    }
}
