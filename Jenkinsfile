pipeline {
    agent any

   environment {
        // Define the path to the SonarQube Scanner executable
        SONAR_SCANNER_HOME = tool name: 'SonarQubeScanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
        PATH = "${SONAR_SCANNER_HOME}/bin:${env.PATH}"
    }

    stages {
        // stage('Build Angular Project') {
        //     steps {
        //         script {
        //                 bat 'npm install -g @angular/cli'
        //                 bat 'npm install'
        //                 bat 'npm run build'
        //             }
        //         } }
            

         stage('SonarQube Analysis') {
            steps {
                // Install SonarQube Scanner
                script {
                    def scannerHome = tool 'SonarQubeScanner'
                    env.PATH = "${scannerHome}/bin:${env.PATH}"
                }

                // Execute SonarQube analysis
                withSonarQubeEnv('SonarQubeServer') 
                {
                    bat 'sonar-scanner'
                }
            }
        }
    }
    
}
        
    

    

