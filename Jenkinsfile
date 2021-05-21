pipeline {
    agent any 
    stages {
        stage('deploy pods') {
            steps {
                withCredentials([file(credentialsId: 'kube.config', variable: 'kube')]) {

               sh "aws eks --region us-east-2 update-kubeconfig --name education-eks-31p1Yair"
                sh "kubectl create namespace dev"
                sh "kubectl apply -f deployment.yaml -n dev  --kubeconfig $kube"
                sh "kubectl apply -f service.yaml -n dev --kubeconfig $kube"
                 }
            }
        }
    }
}
