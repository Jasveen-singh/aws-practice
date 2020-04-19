pipeline {
    agent any 
    stages {
        stage('Repo Clone') { 
            steps {
          sh "export AWS_DEFAULT_REGION=us-east-1"
          
sh "aws cloudformation create-stack --stack-name myVPCTestStack --template-body file://VPC-example.yaml --region 'us-east-1'"
          
          }
        }
        stage('Verify') { 
            steps {
                sh "ls"
            }
        }
        stage('Deploy') { 
            steps {
               sh "ls"
            }
        }
    }
}