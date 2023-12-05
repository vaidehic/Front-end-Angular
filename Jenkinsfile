pipeline {
    agent any

   environment {
        // Define the path to the SonarQube Scanner executable
        SONAR_SCANNER_HOME = "C:/Users/vaidehic/Documents/apps/sonar-scanner-4.0.0.1744-windows"
        PATH = "${SONAR_SCANNER_HOME}/bin:${env.PATH}"
    }

  
    stages {
        stage('Build Angular Project') {
            steps {
              when{
              // changeset 'main'
              }
                script {
                        bat 'npm install -g @angular/cli'
                        bat 'npm install'
                        bat 'npm run build'
                    }
                } }


         stage('SonarQube Analysis') {
            steps {
               script {
       scannerHome = tool 'sonar-scanner'
    }
                // Execute SonarQube analysis
                withSonarQubeEnv('SonarQubeServer') 
                {
                    bat 'C:/Users/vaidehic/Documents/apps/sonar-scanner-4.0.0.1744-windows/bin/sonar-scanner'
                        -D sonar.projectName=Front-End-angular \
                        -D sonar.projectKey=Front-End-angular \
                        -D sonar.projectVersion=1.0 \
                        -D sonar.sources=src \
                        -D sonar.language=ts \
             #exclusions
                        -D  sonar.exclusions=node_modules/*,**/*.spec.ts \

          #coverage reporting
                        -D sonar.typescript.lcov.reportPaths=coverage/lcov.info \
                        -D sonar.host.url=http://172.27.59.109:9000/ \
                        -D sonar.login=accc74edb04d69f56282f915fd081fccde3e54b1 \
                }
            }
        }

        

      
    }
    
}
        
    

    

