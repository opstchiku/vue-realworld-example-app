pipeline {
    agent any

    stages {
        stage('Install') {
            steps {
                sh "yarn install"
            }
        }
        stage('Build') {
            steps {
                sh "yarn run build"
            }
        }
        stage('Test') {
            steps {
                sh "yarn run test"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deployed!!"
            }
        }
    }
}
