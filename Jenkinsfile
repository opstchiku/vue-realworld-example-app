pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                sh """
                    whoami
                    pwd
                    echo $PATH
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
