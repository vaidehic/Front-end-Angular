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
                    // Set up SonarQube environment
                    withSonarQubeEnv('SonarQubeServer') 
                  {
                        // Define SonarQube properties
                        withSonarQubeProperties([
                            'sonar.projectKey': 'Front-End-angular',
                            'sonar.projectName': 'Front-End-angular:a1',
                            'sonar.sources': 'src',
                            'sonar.tests': 'test',
                            'sonar.language': 'js',
                            ' sonar.typescript.lcov.reportPaths':'coverage/lcov.info' ,
                            ' sonar.host.url':'http://172.27.59.109:9000/ ',
                            ' sonar.login':'accc74edb04d69f56282f915fd081fccde3e54b1 '
                        ]) {
                            // Execute SonarQube Scanner
                             bat 'C:/Users/vaidehic/Documents/apps/sonar-scanner-4.0.0.1744-windows/bin/sonar-scanner'
                           }
                    }
                }
            }
        }
    

    //      stage('SonarQube Analysis') {
    //         steps {
    // //            script {
    // //    scannerHome = tool 'sonar-scanner'
    // // }
    //             // Execute SonarQube analysis
    //             withSonarQubeEnv('SonarQubeServer') 
    //           {
    //               //Define Sonarqube properties
    //               withSonarQubeProperties
    //               ([
                    
    //                     ' sonar.projectName':'Front-End-angular',
    //                     ' sonar.projectKey':'Front-End-angular' ,
    //                     ' sonar.projectVersion':'1.0' ,
    //                     ' sonar.sources':'src' ,
    //                     ' sonar.language':'ts' ,
    //          // exclusions'
    //                     ' sonar.exclusions':'node_modules/*,**/*.spec.ts' ,

    //       // coverage reporting
    //                     ' sonar.typescript.lcov.reportPaths':'coverage/lcov.info' ,
    //                     ' sonar.host.url':'http://172.27.59.109:9000/ ',
    //                     ' sonar.login':'accc74edb04d69f56282f915fd081fccde3e54b1 '
    //                ]) 
    //               {
    //                  bat 'C:/Users/vaidehic/Documents/apps/sonar-scanner-4.0.0.1744-windows/bin/sonar-scanner'
    //               }
    //             }
    //         }
    //      }
      
    
}
}
        
    

    

