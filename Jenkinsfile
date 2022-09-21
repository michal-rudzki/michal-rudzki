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

  }
}