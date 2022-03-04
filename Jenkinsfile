pipeline {
  agent none
  stages {
    
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t animeshj123/my-java-app:latest .'
      }
    }
    stage('Docker Push') {
      agent any
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerHub', rajesh@1: 'dockerHubPassword', animeshj123: 'dockerHubUser')]) {
          sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push animeshj123/my-java-app:latest'
        }
      }
    }
  }
}