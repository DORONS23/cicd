pipeline {
    agent any

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
                sh "echo authenticating..."
            }
        }

        stage("Push to Registry") {
            steps{
                sh "echo Pushing..."
            }
        }
        
        stage("Cleanup") {
            steps{
                sh "echo cleanup.."
            }
        }
    }
}
