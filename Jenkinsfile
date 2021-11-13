pipeline {
    agent any

    stages {
        
        stage('Build and push images ') {
            steps {
                sh "sudo docker login -u '$Dockerhub_username' -p '$Dockerhub_password'"

                sh "sudo docker build -t muhammadatef/BakeHouse:latest -t muhammadatef/BakeHouse:\$(git rev-parse HEAD) -f ."
                sh "sudo docker push muhammadatef/BakeHouse:latest" 
                sh "sudo docker push muhammadatef/BakeHouse:\$(git rev-parse HEAD)" 

                
            }
        }
        
        stage('Deploy using k8s') {
            
            steps {
                sh "echo hey"
            }
        }
    }
}
