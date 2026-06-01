pipeline{
    agent any
    environment{
        IMAGE_NAME="amvar0909/myapp"
    }
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
        stage('Docker Build'){
            steps{
                bat 'docker build -t %IMAGE_NAME%:latest'
            }
        }
        stage('Docker Push'){
            steps{
                withCredentials([
                    usernamePassword(
                        credentialsId: 'dockerhub-creds'
                        usernameVariable: 'DOCKER_USER'
                        passwordVariable: 'DOCKER_PASS'
                    )
                ]){
                    bat 'docker login -u %DOCKER_USER% -p %DOCKER_PASS%'
                    bat 'docker push %IMAGE_NAME%:latest'
                }
            }
        }
    }
}