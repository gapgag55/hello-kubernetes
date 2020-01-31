pipeline {
  environment {
    dockerImage = ''
  }
  agent any
  stages {
    stage('Build Image') {
      steps {
        script {
          dockerImage = docker.build "imkopkap/hello-kubernetes"
        }
      }
    }
    stage('Push Image') {
      steps {
        script {
          docker.withRegistry( '', 'dockerhub' ) {
            dockerImage.push('latest')
          }
        }
      }
    }
  }
}