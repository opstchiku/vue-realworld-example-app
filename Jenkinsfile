pipeline {
    agent any

    tools {nodejs "node"}

    stages {
        stage('Install') {
            steps {
                sh "yarn install"
            }
        }
        stage('Replace backend') {
            steps {
                sh """
                    sed -i -e "s/https.*api/http:\\/\\/${params.host}:10080\\/api/g" src/common/config.js
                """
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
                        rsync --delete -e 'ssh -o StrictHostKeyChecking=no' --rsync-path='sudo rsync' \
                         -ahv dist/ ${params.user}@${params.host}:/usr/share/nginx/html
                    """
                }
            }
        }
    }
}
