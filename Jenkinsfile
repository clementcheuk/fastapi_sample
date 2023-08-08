pipeline {
    agent any
    
    environment {
        GITLAB_TOKEN = credentials("GITLAB_TOKEN")
        DOCKERHUB_CREDENTIALS_PSW = credentials("DOCKERHUB_CREDENTIALS_PSW")
        IMAGE_VERSION="3"
    }

    stages{
       
        stage("Build docker image"){
            steps{
                // need to use docker-compose, use docker to build not able to save to local registry
                sh '''
                echo "build image"
                # docker-compose build --no-cache
                '''
            }
        }
        
    }    
}