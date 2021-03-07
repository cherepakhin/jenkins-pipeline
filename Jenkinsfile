pipeline {
  agent {
    docker {
      image 'maven:3'
    }

  }
  stages {
    stage('Example Build') {
      agent {
        docker 'maven:3-alpine'
      }
      steps {
        echo 'Hello, Maven'
        sh 'mvn --version'
      }
    }

  }
}