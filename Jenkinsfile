pipeline {
    agent any

    stages {
        stage("Git Checkout") {
            step{
                sh "echo checking out..."
            }
        }

        stage("Build") {
            steps{
                sh "echo building"
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