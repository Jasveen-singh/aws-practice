pipeline {
    agent any 
	options {
        timeout(time: 5) 
    }
    stages {
        stage('Repo Clone') { 
            steps {
          sh "export AWS_DEFAULT_REGION=us-east-1"
          
sh "aws cloudformation create-stack --stack-name myVPCTestStack --template-body file://VPC-example.yaml --region 'us-east-1'"
          
          }
        }
        stage('Verify') { 
            steps {
			while(true)
                sh "aws cloudformation describe-stacks --stack-name myVPCTestStack | grep CREATE_COMPLETE"
				print "Checking for stack creation status"
            }
        }
        stage('Deploy') { 
            steps {
               sh "aws cloudformation describe-stacks --stack-name myVPCTestStack"
            }
        }
    }
}