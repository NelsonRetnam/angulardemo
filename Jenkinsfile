pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
  
   stage('Upload') {
        dir('C:\Users\asusn\.jenkins\workspace\angular1\dist\ang-app'){
            pwd(); //Log current directory
            withAWS(region:'us-east-2',credentials:'AWS_Credentials') {
                 def identity=awsIdentity();//Log AWS credentials
                // Upload files from working directory 'dist' in your project workspace
                s3Upload(bucket:"angular-s3-app", workingDir:'dist', includePathPattern:'**/*');
            }

        };
    }
}
