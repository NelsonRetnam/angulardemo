pipeline {
  agent any
  
  environment {
      PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Program Files\\Git\\bin;C:\\Program Files\\nodejs\\node_modules\\npm\\bin"
  }
    
  stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Build') {
          steps {
                sh 'pwd'
                sh 'npm install'
                sh 'ng build --prod'
          }
        }
    }
}
