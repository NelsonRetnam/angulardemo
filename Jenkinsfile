pipeline {
  agent any
  
  tools { nodejs "nodejs" }
  
  environment {
      PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Program Files\\Git\\bin"
  }
    
  stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Build') {
          steps {
                sh 'npm install'
                sh 'ng build --prod'
          }
        }
    }
}
