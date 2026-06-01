pipeline {
  agent any
  stages {
    stage('Build') {
      steps { sh 'docker build -t amvar0909/myapp:latest .' }
    }
    stage('Push') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub', 
          usernameVariable: 'USER', passwordVariable: 'PASS')]) {
          sh 'docker login -u $USER -p $PASS'
          sh 'docker push yourhub/myapp:latest'
        }
      }
    }
  }
}