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
              s3Upload(bucket:"viacom123", path:'path/to/targetFolder/', includePathPattern:'**/*', workingDir:'dist', excludePathPattern:'**/*.svg,**/*.jpg')
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
