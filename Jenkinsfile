pipeline {
    environment {
        registry = "muhammadatef/bakehouse"
        registryCredential = 'dockerhub_id'
        dockerImage = ''
        }
    agent any

    stages {
        
        stage('Build and push images ') {
            steps {

                sh " docker build -t muhammadatef/BakeHouse:latest -t muhammadatef/BakeHouse:\$(git rev-parse HEAD) -f ."
                sh " docker push muhammadatef/BakeHouse:latest" 
                sh " docker push muhammadatef/BakeHouse:\$(git rev-parse HEAD)" 

                
            }
        }
        
        stage('Deploy using k8s') {
            
            steps {
                sh "echo hey"
            }
        }
    }
}
