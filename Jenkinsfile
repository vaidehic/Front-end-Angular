pipeline {
    agent any

   environment {
        // Define the path to the SonarQube Scanner executable
        SONAR_SCANNER_HOME = "C:/Users/vaidehic/Documents/sonar-scanner-4.0.0.1744-windows"
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
               script {
       scannerHome = tool 'sonar-scanner'
    }
                // Execute SonarQube analysis
                withSonarQubeEnv('SonarQubeServer') 
                {
                    bat 'C:/Users/vaidehic/Documents/sonar-scanner-4.0.0.1744-windows/bin/sonar-scanner'
                }
            }
        }
    }
    
}
        
    

    

