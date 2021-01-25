properties([pipelineTriggers([githubPush()])])

pipeline {
    agent { 
      docker {
        image 'hashicorp/terraform:light'
        args  '--entrypoint='
      }
    }


    options {
       withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-key', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])	
    }


    environment {
     AWS_REGION = "eu-west-3"
    }
}
