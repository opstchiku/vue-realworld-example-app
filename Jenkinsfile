pipeline {
    agent any

    tools {nodejs "node"}

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
                sshagent(['identity']) {
                    sh """
                        rsync -e "ssh -o StrictHostKeyChecking=no" -ahv \
                        dist/ ${params.user}@${params.host}:/usr/share/nginx/html
                    """
                }
            }
        }
    }
}
