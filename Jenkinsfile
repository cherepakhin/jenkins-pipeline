pipeline {
  agent {
    docker {
      image 'fabric8/java-alpine-openjdk11-jre'
      args '-v /root/.m2:/root/.m2 -v /var/run/docker.sock:/var/run/docker.sock'
    }

  }
  stages {
    stage('Build') {
      steps {
        git 'https://github.com/cherepakhin/jenkins-pipeline'
        sh 'java -version'
      }
    }

    stage('Test') {
      steps {
        sh 'java -version'
      }
    }

  }
}