pipeline {
    
    agent any

    stages {

        stage('Build and push images ') {
            steps {

                withCredentials([usernamePassword(credentialsId: 'dockerhub_id', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                // available as an env variable, but will be masked if you try to print it out any which way
                // note: single quotes prevent Groovy interpolation; expansion is by Bourne Shell, which is what you want
                sh 'echo $PASSWORD'
                // also available as a Groovy variable
                echo USERNAME
                // or inside double quotes for string interpolation
                echo "username is $USERNAME"
                sh "sudo docker build -t muhammadatef/bakehouse:latest ."
                sh "sudo docker login -u '$USERNAME' -p '$PASSWORD'"

                sh "sudo docker push muhammadatef/bakehouse:latest" 
                }

            }
        }
        
        stage('Deploy using k8s') {
            
            steps {
                sh "/usr/local/bin/kubectl apply -f ."
            }
        }
    }
}
