pipeline {
    agent {
        docker {
            image 'node:18-alpine'
            reuseNode true
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build stage'
                sh '''
                    npm install
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