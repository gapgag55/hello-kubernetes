pipeline {
  environment {
    registry = "imkopkap/hellokubernetes"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent { dockerfile true }
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
    // stage('Test') {
    //   steps {
    //     echo 'Testing..'
    //   }
    // }
    // stage('Deploy Image') {
    //   steps{
    //     script {
    //       docker.withRegistry( '', registryCredential ) {
    //         dockerImage.push()
    //       }
    //     }
    //   }
    // }
    // stage('Deploy') {
    //   steps {
    //     echo 'Deploying....'
    //   }
    // }
  }
}