pipeline {
  environment {
    dockerImage = ''
  }
  agent { dockerfile true }
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
          dockerImage.push('latest')
        }
      }
    }
  }
}