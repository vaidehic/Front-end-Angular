pipeline {
    agent any

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
        
    

    

