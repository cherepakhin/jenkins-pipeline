pipeline {
//    agent none
    agent {
        dockerfile {
            label 'agent1'
            filename 'Dockerfile.java8'
            dir 'jenkins_build'
        }
    }
    stages {
        stage('Java8') {
//            agent {
//            }
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