pipeline {
  agent {
    node {
      label 'jenkins02'
    }

  }
  stages {
    stage('check docker') {
      steps {
        sh 'docker --version'
      }
    }

    stage('checking hostname') {
      steps {
        sh 'hostname'
      }
    }

  }
}