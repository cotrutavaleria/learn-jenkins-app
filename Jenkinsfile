pipeline {
    agent any

    stages {
         stage('Update Browserslist DB') {
            steps {
                script {
                    sh 'npx update-browserslist-db@latest'
                }
            }
        }
        stage('Build') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
