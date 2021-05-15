pipeline {
    agent any 
    environment {
        username = credentials('Dockerhub_username')
        password = credentials('Dockerhub_password')
    }
    stages {
        stage('Build and push images ') {
            steps {
                sh "sudo docker login -u '$username' -p '$password'"
                sh "sudo docker build -t muhammadatef/bakehouse:latest . "
                sh "sudo docker push muhammadatef/bakehouse:latest" 
                echo "bakehouse build and push seccessfully"                
            }
        }
    }
}
