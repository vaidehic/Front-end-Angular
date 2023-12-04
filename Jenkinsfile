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
                    
                          withSonarQubeEnv('SonarQubeServer') {
                             bat 'sonar-scanner'
                }
                        }
                    }
                }
    }
}
        
    

    

