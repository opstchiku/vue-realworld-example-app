pipeline {
    agent {
        docker {
            image 'node:12-alpine'
        }   
    }

    stages {
        stage('Prepare') {
            steps {
                sh "npm install -g yarn"
            }
        }
        stage('Install') {
            steps {
                sh "yarn install"
            }
        }
        stage('Test') {
            steps {
                sh "yarn run test"
            }
        }
        stage('Build') {
            steps {
                sh "yarn run build"
            }
        }
    }
}
