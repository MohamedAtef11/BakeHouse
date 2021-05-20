pipeline {
    agent any 
    stages {
        stage('deploy pods') {
            steps {
                withCredentials([file(credentialsId: 'kube.config', variable: 'kube.config')]) {

                sh "kubectl apply -f deployment.yaml -n eks-ns --kubeconfig=$kube.config "
                sh "kubectl apply -f service.yaml -n eks-ns --kubeconfig=$kube.config " 
                 }
            }
        }
    }
}
