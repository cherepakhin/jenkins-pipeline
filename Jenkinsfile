pipeline {
    agent none
//    agent {
//        label 'agent1'
//    }
    stages {
        stage('check docker') {
            agent {
                label 'master'
            }
            steps {
                sh 'docker version'
                sh 'kubectl version'
            }
        }
        stage('Java8') {
            agent {
                docker {
                    image 'maven:3-alpine'
                    args "-v /root/.m2:/root/.m2 -v /var/run/docker.sock:/var/run/docker.sock"
                }
            }
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
                    reuseNode true
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