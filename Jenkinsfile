pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Contoh build script
                echo 'Building the application...'
                // Misalnya, untuk aplikasi Node.js:
                // sh 'npm install && npm run build'
            }
        }

        stage('Test') {
            steps {
                // Contoh menjalankan tes
                echo 'Running tests...'
                // Misalnya, untuk aplikasi Node.js:
                // sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                // Contoh deployment
                echo 'Deploying the application...'
            }
        }
    }
}
