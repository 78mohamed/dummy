

pipeline {
   agent any
   environment {
        registry = "140744541048.dkr.ecr.us-east-1.amazonaws.com/myreg"
    }
   stages {
      
      
      stage('Build docker') {
         steps {
            script {
          dockerImage = docker.build registry
        
         }
         }
      }
      stage('push docker') {
         steps {
            script {
          sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 140744541048.dkr.ecr.us-east-1.amazonaws.com'
          sh 'docker push 140744541048.dkr.ecr.us-east-1.amazonaws.com/myreg:myapp2'
        
         }
         }
      }
      
   }
}
