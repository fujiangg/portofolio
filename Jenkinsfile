pipeline {
    agent any

    environment {
        VUGEN_SCRIPT = 'C:/Users/Administrator/Documents/VuGen/Scripts/WebHttpHtml1/WebHttpHtml1.lrs'
        CONTROLLER_SCENARIO = 'C:/Users/Administrator/Documents/Controller/scenario/Scenario1.lrc'
        ANALYSIS_PATH = 'C:/Users/Administrator/Documents/Session1/Session1.lra'
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone repository
                checkout scm
            }
        }

        // stage('Build') {
        //     steps {
        //         // Contoh build script
        //         echo 'Building the application...'
        //         // Misalnya, untuk aplikasi Node.js:
        //         // sh 'npm install && npm run build'
        //     }
        // }

        // stage('Test') {
        //     steps {
        //         // Contoh menjalankan tes
        //         echo 'Running tests...'
        //         // Misalnya, untuk aplikasi Node.js:
        //         // sh 'npm test'
        //     }
        // }

        stage('Setup') {
            steps {
                script {
                    // Menyiapkan direktori atau environment jika diperlukan
                    echo 'Preparing the environment for LoadRunner testing...'
                }
            }
        }

        stage('Run LoadRunner VuGen Script') {
            steps {
                script {
                    // Jalankan script VuGen untuk memastikan script berjalan
                    echo "Running VuGen script from: ${env.VUGEN_SCRIPT}"
                    bat """ 
                    "C:/Program Files (x86)/OpenText/LoadRunner/bin/VuGen.exe" -run -script "${env.VUGEN_SCRIPT}" 
                    """
                }
            }
        }

        stage('Run Controller Scenario') {
            steps {
                script {
                    // Jalankan scenario dengan Controller
                    echo "Running scenario from Controller at: ${env.CONTROLLER_SCENARIO}"
                    bat """
                    "C:/Program Files (x86)/OpenText/LoadRunner/bin/Wlrun.exe" -run -scenario "${env.CONTROLLER_SCENARIO}"
                    """
                }
            }
        }

        // stage('Analyze Results') {
        //     steps {
        //         script {
        //             // Jalankan analisis hasil tes
        //             echo "Analyzing results at: ${env.ANALYSIS_PATH}"
        //             bat """
        //             "C:/Program Files (x86)/OpenText/LoadRunner/bin/AnalysisUI.exe" -run -session "${env.ANALYSIS_PATH}"
        //             """
        //         }
        //     }
        // }

        stage('Deploy') {
            steps {
                // Contoh deployment
                echo 'Deploying the application...'
            }
        }
    }
}
