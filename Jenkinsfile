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
                      npm install
                      npm run ng build
                      mv dist/test/* /var/www/html'''
          }
        }
        stage('Upload') {
          steps {
              echo 'hello'
              sh '''
              cd dist/ang-app/
              pwd 
              ls '''
              s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, 
                entries: [[bucket: 'vote123', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, 
                           managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-east-2', showDirectlyInBrowser: false, sourceFile: 'dist/ang-app/*.*', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 'S3_Deploy', userMetadata: []
              
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
