pipeline{
    agent any
    stages{
        stage('Checkout'){
            steps{
                echo "Checking out source code"
            }
        }
        stage('Build'){
            steps{
                echo "Building application"
            }
        }
        stage('Test'){
            steps{
                error("Tests failed")
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying application"
            }
        }
    }
}