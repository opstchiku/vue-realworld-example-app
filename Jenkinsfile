pipeline {
    agent any

    stages {
        stage('Echo') {
            steps {
                sh """
                    pwd
                    ls -la
                """
            }
        }
        stage('Test') {
            steps {
                sh """
                    yarn install
                    yarn run test
                """
            }
        }
        stage('Build') {
            steps {
                sh """
                    yarn run build
                """
            }
        }
    }
}
