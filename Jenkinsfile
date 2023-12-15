pipeline {
 
agent any
   environment {
        // Define the path to the SonarQube Scanner executable
        SONAR_SCANNER_HOME = "C:/Users/vaidehic/Documents/apps/sonar-scanner-4.0.0.1744-windows"
        PATH = "${SONAR_SCANNER_HOME}/bin:${env.PATH}"
        SONAR_TOKEN_CREDS = credentials('sonarqube-token')
    }
   triggers {
        pollSCM('H * * * *')
    }
  
 //   agent
	// {
	// node{
	// 	label 'vaidehi-node'
	// }
	// }
    stages {
        stage('Build Angular Project') {
            steps {
              
                script {
                        bat 'npm install -g @angular/cli'
                        bat 'npm install'
                        bat 'npm run build'
                      }
                } 
        
        }

        stage('SonarQube Analysis') 
      {
            steps 
         {
                script 
             {
                withCredentials([string(credentialsId: 'sonarqube-token', variable: 'SONAR_TOKEN')]) 
                          {
                        // Use SONAR_TOKEN in your build steps
                       // echo "SonarQube Token: ${SONAR_TOKEN}"
                 
                            // Execute SonarQube Scanner
                             
                             bat "C:/Users/vaidehic/Documents/apps/sonar-scanner-4.0.0.1744-windows/bin/sonar-scanner -Dsonar.login=${SONAR_TOKEN_CREDS} -Dsonar.projectKey=Front-End-angular -Dsonar.projectName='Front-End-angular'"
                           }
              }
           }
      }
        }
    

   
      
    

}
        
     
    
    

    

