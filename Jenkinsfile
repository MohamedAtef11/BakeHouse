pipeline {
    agent any 
    environment {
        Dockerhub_username     = credentials('Dockerhub_username')
        Dockerhub_password = credentials('Dockerhub_password')
    }
    stages {
        stage('Build and push images ') {
            steps {
                sh "sudo docker login -u '$Dockerhub_username' -p '$Dockerhub_password'"
                sh "sudo docker build -t muhammadatef/bakehouse:latest . "
                sh "sudo docker push muhammadatef/bakehouse:latest" 
                echo "bakehouse build and push seccessfully"                
            }
        }
    }
}