pipeline {
  agent {
    docker {
      image 'ubuntu/apach2'
      args '''RUN echo "Django Project"
RUN apt-get -y update
RUN apt-get -y upgrade
RUN echo "Install python"
RUN apt-get -y install python3
RUN apt-get -y install python3-pip'''
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