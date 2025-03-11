pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    sudo chown -R 116:119 "/.npm"
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
