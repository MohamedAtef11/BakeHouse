pipeline {
    
    agent any

    stages {

        stage('Build and push images ') {
            steps {

                withCredentials([usernamePassword(credentialsId: 'dockerhub_id', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
               
                sh " docker build -t muhammadatef/bakehouse:latest ."
                sh " docker login -u '$USERNAME' -p '$PASSWORD'"
                sh " docker push muhammadatef/bakehouse:latest" 
                 
                }

            }
        }
        
        // stage('Deploy using k8s') {
            
        //     steps {
        //         sh "/usr/local/bin/kubectl delete --kubeconfig=/var/lib/jenkins/config -f ."
        //         sh "/usr/local/bin/kubectl  apply --kubeconfig=/var/lib/jenkins/config -f ."
        //     }
        // }
    }
}
