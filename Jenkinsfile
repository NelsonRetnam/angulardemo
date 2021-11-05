pipeline {
  agent any
  
  environment {
     PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Program Files\\Git\\bin;C:\\Program Files\\nodejs\\;C:\\Users\\USER_NAME\\AppData\\Roaming\\npm\\;C:\\Program Files\\PowerShell\\7"
  }
  
  stages {
        stage('Build') {
          steps {sh '''
                      pwd
                      npm run ng build'''
          }
        }
        stage('Upload') {
          steps {
              sh '''
                  cd dist/ang-app/
                  pwd 
                  ls'''
                     
           s3Upload(file:'dist/ang-app/*.*', bucket:'viacom123', path:'/', acl:'PublicRead')
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
