pipeline {
  environment {
    registry = "imkopkap/hellokubernetes"
    registryCredential = 'dockerhub'
  }

  agent {
    docker { image 'node:7-alpine' }
  }
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        
        script {
          docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Test') {
      steps {
        echo 'Testing..'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }
  }
}