pipeline {
  agent {
    node {
      label 'jenkins02'
    }

  }
  stages {
    stage('check docker') {
      parallel {
        stage('check docker') {
          steps {
            sh 'docker --version'
          }
        }

        stage('git clone') {
          steps {
            sh 'hostname'
          }
        }

      }
    }

  }
}