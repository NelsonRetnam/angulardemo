pipeline {
  agent any
  
  environment {
      PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Program Files\\Git\\bin;C:\\Program Files\\nodejs\\;C:\\Users\\USER_NAME\\AppData\\Roaming\\npm"
  }
    
  stages {
        stage('Build') {
          steps {sh '''
                      cd ${WORKSPACE}
                      pwd
                      npm run ng build'''
          }
        }
        stage('Upload') {
          steps {
              echo 'hello'
              s3Upload entries: [[bucket: 'vote123', excludedFile: '/dist/ang-app/', selectedRegion: 'us-east-2', sourceFile: '**/dist/ang-app/*.*', 
                                  storageClass: 'STANDARD']], profileName: 'S3_Deploy'
              
          }
        }
        /*stage('Test') {
          parallel {
            stage('Static code analysis') {
                steps { sh 'npm run-script lint' }
            }
            stage('Unit tests') {
                steps { sh 'npm run-script test' }
            }
          }
       }*/
    }
}
