pipeline {
    agent none
//    agent {
//        label 'agent1'
//    }
    stages {
        stage('Java8') {
            agent {
                docker {
                    image 'maven:3-alpine'
                }
            }
            steps {
                echo "${env.NODE_NAME}"
                sh 'pwd'
                sh 'env'
                sh 'java -version'
                sh 'docker version'
            }
        }
        stage('Java11') {
            agent {
                dockerfile {
                    filename 'Dockerfile.java11'
                    dir 'jenkins_build'
                    reuseNode true
                }
            }
            steps {
                echo "${env.NODE_NAME}"
                sh 'tree'
                sh 'env'
                sh 'ls -l'
                sh 'java -version'
                sh 'docker version'
            }
        }
    }
}