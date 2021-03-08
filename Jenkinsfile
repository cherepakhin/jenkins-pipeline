pipeline {
    agent {
        dockerfile {
            filename 'Dockerfile.java8'
            dir 'jenkins_build'
            args "-v /root/.m2:/root/.m2 -v /var/run/docker.sock:/var/run/docker.sock"
        }
    }
//    agent none
    stages {
        stage('Java8') {
//            agent {
//                label 'agent1'
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