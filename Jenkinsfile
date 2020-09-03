pipeline {
    agent any

    stages {
        stage('Prepare') {
            sh """
                npm install -g yarn
            """
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
