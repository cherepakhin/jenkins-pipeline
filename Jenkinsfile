pipeline {
//    agent none
    agent {
        dockerfile {
            filename 'Dockerfile.java8'
            dir 'build'
        }
    }
    stages {
        stage('Java8') {
            steps {
                echo 'Java8'
                sh 'java -version'
            }
        }
        stage('Java11') {
            agent {
                dockerfile {
                    filename 'Dockerfile.java11'
                    dir 'build'
                }
            }
            steps {
                echo 'Java11'
                sh 'java -version'
            }
        }
    }
}