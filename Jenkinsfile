pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Upload') {
          steps {
            dir("C:\Program Files\Git\bin"){
                sh "pwd"
            }
          }
        }
    }
}
