pipeline {
    agent any 
    stages {
        stage('deploy pods') {
            steps {
                withCredentials([file(credentialsId: 'kube.config', variable: 'kube')]) {

                sh "kubectl apply -f deployment.yaml "
                sh "kubectl apply -f service.yaml  " 
                 }
            }
        }
    }
}
