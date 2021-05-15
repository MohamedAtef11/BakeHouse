pipeline {
    agent any 
    stages {
        stage('Build and push images ') {
            steps {
                sh "sudo docker login -u credentials('Dockerhub_username') -p credentials('Dockerhub_password')"

                sh "sudo docker build -t muhammadatef/bakehouse:latest . "
                sh "sudo docker push muhammadatef/bakehouse:latest" 
                echo "bakehouse build and push seccessfully"                
            }
        }
    }
}