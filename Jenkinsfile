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
                echo 'Build stage'
                sh '''
                    npm ci
                    npm run build
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Test stage'
                sh '''
                    test -f build/index.html
                    npm test
                '''
            }
        }
    }
}