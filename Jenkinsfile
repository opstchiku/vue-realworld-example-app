pipeline {
    agent any

    stages {
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
