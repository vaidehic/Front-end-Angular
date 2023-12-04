pipeline {
    agent any

    stages {
        stage('Build Angular Project') {
            steps {
                script {
                 
                        bat 'npm install'
                        bat 'npm run build'
                    }
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    
                            // Run SonarQube scanner
                            bat 'sonar-scanner'
                        }
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline successfully executed!'
        }
        failure {
            echo 'Pipeline failed. Check the console output for details.'
        }
    }
}
