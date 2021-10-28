pipeline {
    agent any
  
  environment {

    PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Program Files\\Git\\bin"

  }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Upload') {
          steps {
                bat ''' ECHO Hello World  '''
                sh "pwd"
          }
        }
    }
}
