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
                echo 'Hello World'
            }
        }
        stage('Test') {
            steps {
                echo 'Test stage'
                sh '''
                    npm run build
                    test -f build/index.html
                    npm test
                '''
            }
        }
    }
}