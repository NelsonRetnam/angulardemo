pipeline {
    agent any
  
  environment {

    PATH = "C:\\WINDOWS\\SYSTEM32"

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
          }
        }
    }
}
