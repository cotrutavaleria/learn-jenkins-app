pipeline {
    agent any

    stages {
        stage('Test Docker') {
            steps {
                script {
                    docker.image('node:18-alpine').inside {
                        sh '''
                            node --version
                            npm --version
                        '''
                    }
                }
            }
        }
    }
}
