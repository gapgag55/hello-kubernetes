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
    stage('Deploy Development') {
      steps {
        sh 'kubectl apply -f dev-deployment.yml';
        sh 'kubectl apply -f dev-service.yml';
      }
    }
  }
}