pipeline {
    agent {
        dockerfile {
            filename 'Dockerfile.java8'
            dir 'build'
            label 'lbl-java8'
        }
    }

    agent {
        dockerfile {
            filename 'Dockerfile.java11'
            dir 'build'
            label 'lbl-java11'
        }
    }
    agent none
    stages {
        stage('Build1') {
            agent {label 'lbl-java8'}
            steps {
                checkout scm
                sh 'java -version'
            }
        }
        stage('Test') {
            agent {label 'lbl-java11'}
            steps {
                sh 'java -version'
            }
        }
    }
}