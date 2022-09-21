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
  environment {
    GITHUB_TOKEN = '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'
  }
}