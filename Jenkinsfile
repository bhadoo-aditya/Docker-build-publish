pipeline {
  tools {
    dockerTool 'docker'
  }
  environment {
    registry = "https://registry.hub.docker.com"
    registryCredential = "dockerhub"
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git branch: 'main', changelog: false, poll: false, url: 'https://github.com/bhadoo-aditya/Docker-build-publish.git'
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
