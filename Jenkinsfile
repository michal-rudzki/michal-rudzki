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

        stage('remove doc. conrtainrs and images') {
          steps {
            sh '''export doc_img_count=$(docker image ls -a | grep [a-z][0-9] | wc -l)
export doc_con_count=$(docker container ls -a | grep [a-z][0-9] | wc -l)


if [ $doc_con_count -gt 0 ]
then
  docker container ls | grep [a-z][0-9] | awk \'{print $2}\' | while read line
  do
    docker container rm $line -f
  done
  echo "Containers are removed..."
fi

if [ $doc_img_count -gt 0 ]
then
  docker images --all | grep [a-z][0-9] | awk \'{print $3}\' | while read line
  do
    docker image rm $line -f
  done
  echo "Images are remove..."
fi
'''
          }
        }

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
        dir(path: 'michal-rudzki/docker') {
          sh 'docker build -t ubuntu-apache2:1.0 .'
          sh 'docker container run --rm -d --name Web2.0 -p 7080:80 -d ubuntu-apache2:1.0 '
        }

      }
    }

  }
  environment {
    GITHUB_TOKEN = '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'
    TZ = 'Europe/Warsaw'
  }
}