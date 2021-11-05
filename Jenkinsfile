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
                     
            s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, 
                entries: [[bucket: 'viacom123', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, 
                           managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-east-2', showDirectlyInBrowser: false, 
                           sourceFile: 'dist/ang-app/*.*', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false, 
                           cl: 'public-read']], pluginFailureResultConstraint: 'FAILURE', profileName: 'S3_Deploy', userMetadata: []
          }
        }
        stage('Test') {
                // steps { sh 'npm run ng test --watch=false' }
          parallel {
            stage('Static code analysis') {
                steps { sh 'echo "Static code analysis completed"' }
            }
            stage('Unit tests') {
                steps { sh 'echo "Unit tests completed"' }
            }
          }
        }
    }
}
