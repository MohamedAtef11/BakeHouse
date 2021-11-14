pipeline {
    
    agent any

    stages {

        stage('Build and push images ') {
            steps {

                withCredentials([usernamePassword(credentialsId: 'dockerhub_id', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
               
                sh "sudo docker build -t muhammadatef/bakehouse:latest ."
                sh "sudo docker login -u '$USERNAME' -p '$PASSWORD'"
                sh "sudo docker push muhammadatef/bakehouse:latest" 
                }

            }
        }
        
        stage('Deploy using k8s') {
            
            steps {
                sh "/usr/local/bin/kubectl  apply --kubeconfig=/var/lib/jenkins/config -f ."
            }
        }
    }
}
