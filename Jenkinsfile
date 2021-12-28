pipeline {
    agent any
    
     environment {
        
        awscli = "C:\\Program Files\\Amazon\\AWSCLIV2\\awscli"
        appcmd = "C:\\Windows\\System32\\inetsrv"
    }

    stages {
        stage('S3download') {
            steps {
                withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '0e6c4ec2-57e5-4bee-b36b-8de0ab7fdbe8', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])
                {
                  bat 'aws s3 cp  s3://awscli-upload/hi/ConsoleApp.dll D:\\Azuredevops'
                }
            }
        }
        stage('Stop AppWebsite') {
            steps {
                bat 'AppCmd stop site "default"'
            }
        }
    }
}
