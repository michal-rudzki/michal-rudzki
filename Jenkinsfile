pipeline {
  agent none
  stages {
    stage('docker image') {
      steps {
        sh 'docker build -t ubuntu-apache2:1.0 .'
      }
    }

  }
}