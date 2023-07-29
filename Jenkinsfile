pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS=credentials('debbc0c7-01fe-40b9-8a54-48e2d6da52ce')
    }

    stages {
        stage("Git Checkout") {
            steps{
                git branch: 'main', url: 'https://github.com/DORONS23/cicd.git'
            }
        }

        stage("Docker Build") {
            steps{
                sh "docker build -t edorons/timeserver ."
            }
        }

        stage("Authenticate") {
            steps{
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                echo "Login complete..."
            }
        }

        stage("Push to Registry") {
            steps{
                script
                    sh 'docker tag edorons/timeserver docker.io/edorons/efosaserver:$BUILD_ID'
                    sh 'docker push docker.io/edorons/efosaserver:$BUILD_ID'
            }
        }
        
        stage("Cleanup") {
            steps{
                sh 'docker rmi -f $(docker image ls -aq)'
                sh 'docker logout'
            }
        }
    }
}
