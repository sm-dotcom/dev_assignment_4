pipeline {
    agent none

    stages {
        stage('NodeJS Version') {
            agent {
                docker {
                    image 'node:14.1'
                    label 'docker'
                }
            }
            steps {
                script {
                    def version = sh(script: 'node -v', returnStdout: true).trim()
                    echo "Node ${version} sarah"
                }
            }
        }

        stage('Maven Version') {
            agent {
                docker {
                    image 'maven:3.8.6'
                    label 'docker'
                }
            }
            steps {
                script {
                    def version = sh(script: 'mvn -v | grep "Apache Maven"', returnStdout: true).trim()
                    echo "${version} sarah"
                }
            }
        }
    }
}
