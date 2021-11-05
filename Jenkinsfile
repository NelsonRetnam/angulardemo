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
                     
            def identity=awsIdentity();
            s3Upload acl: 'PublicRead', bucket: 'viacom123', file: 'dist/ang-app/*.*', workingDir: '.'
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
