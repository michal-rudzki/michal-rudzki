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
      parallel {
        stage('checking hostname') {
          steps {
            sh 'hostname'
          }
        }

        stage('clone repo') {
          steps {
            sh 'rm -rf *'
            sh 'git clone https://GITHUB_TOKEN@github.com/michal-rudzki/michal-rudzki.git'
          }
        }

      }
    }

    stage('docker image build') {
      steps {
        sh 'cd michal-rudzki/docker'
        sh 'id michal'
      }
    }

  }
  environment {
    GITHUB_TOKEN = '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'
  }
}