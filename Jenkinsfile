pipeline {
  agent {
    docker { image 'node:7-alpine' }
  }
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing..'
      }
    }
    stage('Build Image') {
      steps {
        echo 'Build Image'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }
  }
}