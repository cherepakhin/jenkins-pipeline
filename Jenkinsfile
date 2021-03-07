pipeline {
//    agent {
//        docker {
//            image 'fabric8/java-alpine-openjdk8-jre'
//            args "-v /root/.m2:/root/.m2 -v /var/run/docker.sock:/var/run/docker.sock"
//        }
//    }
    agent {
        docker {
            image 'maven:3'
            args "-v /root/.m2:/root/.m2 -v /var/run/docker.sock:/var/run/docker.sock"
        }
    }
    stages {
        stage('Build1') {
            steps {
                checkout scm
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