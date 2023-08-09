pipeline {
    agent any
    
    environment {
        GITLAB_TOKEN = credentials("GITLAB_TOKEN")
        DOCKERHUB_CREDENTIALS_PSW = credentials("DOCKERHUB_CREDENTIALS_PSW")
        IMAGE_VERSION="1"
        IMAGE_NAME="fastapi_sample"
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

        stage('push image to dockerhub'){
            steps{
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u cheukub --password-stdin'
                // sh 'docker tag fastapi_sample:$IMAGE_VERSION cheukub/fastapi_sample:$IMAGE_VERSION'
                sh 'docker push cheukub/$IMAGE_NAME:$IMAGE_VERSION'
            }
        }
        
    }    
}