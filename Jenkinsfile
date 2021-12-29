pipeline {
    agent any
    
     environment {
        
        awscli = "C:\\Program Files\\Amazon\\AWSCLIV2\\awscli"
        appcmd = "C:\\Windows\\System32\\inetsrv"
    }

    stages {
        stage('S3download') {
            steps {
                withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '7c0bd2d9-0177-4cb4-a32f-bb294c1b81b6',
                                  secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])
                {
                  bat 'aws s3 cp  s3://awscli-upload/hi/ConsoleApp.dll D:\\Azuredevops'
                    echo "The build number is ${env.BUILD_NUMBER}"
                    echo "You can also use \${BUILD_NUMBER} -> ${BUILD_NUMBER}"
                }
            }
        }
        
        stage('stop AppWebsite') {
            steps {
                bat 'C:\\Windows\\System32\\inetsrv\\AppCmd start site "newsite"'
            }
        }
        stage('start AppWebsite') {
            steps {
                bat 'C:\\Windows\\System32\\inetsrv\\AppCmd stop site "newsite"'
            }
        }
    }
}
