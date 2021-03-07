agent {
    dockerfile {
        filename 'Dockerfile.java11'
        dir 'build'
        label 'lbl-java11'
    }
}
agent {
    dockerfile {
        filename 'Dockerfile.java8'
        dir 'build'
        label 'lbl-java8'
    }
}
pipeline {
    agent none
    stages {
        stage('Build1') {
            steps {
                agent {label 'lbl-java8'}
                checkout scm
                sh 'java -version'
            }
        }
        stage('Test') {
            steps {
                agent {label 'lbl-java11'}
                sh 'java -version'
            }
        }
    }
}