pipeline {
  agent any
  stages {
    stage('Build') {
      steps { bat 'docker build -t amvar0909/myapp:latest .' }
    }
    stage('Push') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub', 
          usernameVariable: 'USER', passwordVariable: 'PASS')]) {
          bat 'docker login -u $USER -p $PASS'
          bat 'docker push amvar0909/myapp:latest'
        }
      }
    }
  }
}