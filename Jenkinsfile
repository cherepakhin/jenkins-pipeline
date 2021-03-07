pipeline {
  agent {
    docker {
      image 'maven:3'
    }

  }
  stages {
    stage('Echo') {
      agent {
        docker {
          image 'fabric8/java-alpine-openjdk11-jre'
        }

      }
      steps {
        echo 'hello1'
      }
    }

    stage('java11') {
      agent {
        docker {
          image 'fabric8/java-alpine-openjdk11-jre'
        }

      }
      steps {
        echo 'java'
      }
    }

  }
}