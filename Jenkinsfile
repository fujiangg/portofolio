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

        stage('Test with LoadRunner') {
            steps {
                script {
                    echo 'Running LoadRunner performance tests...'

                    // Menjalankan LoadRunner Controller dengan file skenario
                    bat """
                    Wlrun.exe -Run -TestPath "C:/Users/Administrator/Documents/Controller/scenario/Scenario1.lrs" -ResultName "C:/Users/Administrator/Documents/POC/CI-CD/Controller-Result"
                    """
                }
            }
        }

        stage('Analyze Results') {
            steps {
                script {
                    echo 'Analyzing LoadRunner test results...'

                    // Analisis hasil pengujian menggunakan LRAnalysisLauncher
                    bat """
                    LRAnalysisLauncher.exe -input "C:/Users/Administrator/Documents/POC/CI-CD/Analyze-Result/results.lrr" -output "C:/Users/Administrator/Documents/POC/CI-CD/Analyze-Result"
                    """
                }
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
