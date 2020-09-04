pipeline {
    agent any

    tools {nodejs "node v14"}

    stages {
        stage('Prepare') {
            steps {
                sh """
                    npm install -g yarn
                """
            }
        }
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
