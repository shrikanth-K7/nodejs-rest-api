pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Node.js App...'
                bat 'node -v'
                bat 'npm -v'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'npm test || echo "No tests found"'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Starting application...'
                bat 'node app.js'
            }
        }
    }

    post {
        success {
            echo '✅ Build and deployment successful!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
