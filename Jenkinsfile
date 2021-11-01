pipeline {
  agent any
  
  environment {
      PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Program Files\\Git\\bin;C:\\Program Files\\nodejs\\;C:\\Users\\USER_NAME\\AppData\\Roaming\\npm"
  }
    
  stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Build') {
          steps {sh '''
                      cd ${WORKSPACE}
                      pwd
                      npm run ng build'''
          }
        }
    }
}
