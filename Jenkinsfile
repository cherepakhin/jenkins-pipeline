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
pipeline {
//    agent {
//        docker {
//            image 'fabric8/java-alpine-openjdk8-jre'
//            args "-v /root/.m2:/root/.m2 -v /var/run/docker.sock:/var/run/docker.sock"
//        }
//    }
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
//            agent {
//                docker {
//                    image 'fabric8/java-alpine-openjdk11-jre'
//                    args "-v /root/.m2:/root/.m2 -v /var/run/docker.sock:/var/run/docker.sock"
//                }
//            }
//            agent {
//                docker {
//                    image 'maven:3'
//                    args "-v /root/.m2:/root/.m2 -v /var/run/docker.sock:/var/run/docker.sock"
//                }
//            }
            steps {
                sh 'java -version'
            }
        }
    }
}