pipeline {
  environment {
    registry = "https://registry.hub.docker.com"
    registryCredential = "dockerhub"
  }
  agent any
  stages {
    stage('Cloning Git') {
      node {
        checkout scm
        
      }
    }
    stage('Building image') {
      steps{
        script {
          docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
  }
}
