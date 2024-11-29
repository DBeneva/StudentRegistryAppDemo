pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/DBeneva/StudentRegistryAppDemo'
            }
        }

        stage('Install dependencies') {
            steps {
                script {
                    bat 'npm install'
                }
            }
        }

        stage('Start application') {
            steps {
                script {
                    bat 'start /b npm start'
                }
            }
        }
        
        stage('Run tests') {
            steps {
                script {
                    bat 'npm test'
                }
            }
        }
    }

    post {
        always {
            echo 'CI pipeline completed'
        }
    }
}