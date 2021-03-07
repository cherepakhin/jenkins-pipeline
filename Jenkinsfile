pipeline {
    agent none
    stages {
        stage('Java8') {
            agent {
                dockerfile {
                    filename 'Dockerfile.java8'
                    dir 'build'
                }
            }
            steps {
                echo "${env.NODE_NAME}"
                echo 'Java8'
                sh 'env'
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
                echo "${env.NODE_NAME}"
                echo 'Java11'
                sh 'env'
                sh 'ls -l'
                sh 'java -version'
            }
        }
    }
}