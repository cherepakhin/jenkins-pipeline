pipeline {
//    agent none
    agent {
        label 'agent1'
    }
    stages {
        stage('Java8') {
            steps {
                echo "${env.NODE_NAME}"
                sh 'pwd'
                sh 'env'
                sh 'java -version'
            }
        }
        stage('Java11') {
            agent {
                dockerfile {
                    filename 'Dockerfile.java11'
                    dir 'jenkins_build'
                }
            }
            steps {
                echo "${env.NODE_NAME}"
                sh 'tree'
                sh 'env'
                sh 'ls -l'
                sh 'java -version'
            }
        }
    }
}