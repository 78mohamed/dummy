

pipeline {
   agent any
    parameters {
        string(name: 'access', description: 'aws access key')
        string(name: 'secret', description: 'aws secret key')
    }
   stages {
      
      
      stage('configure aws and access eks cluster') {
         steps {
            script {
          sh "aws configure set aws_access_key_id ${params.access} && aws configure set aws_secret_access_key ${params.secret}"
          sh "aws eks --region us-east-1 update-kubeconfig --name myeks"
        
         }
         }
      }
      
      stage('deploy kubernates files') {
         steps {
            script {
          sh "kubectl apply ns.yml"
        
         }
         }
      }
      
      
      
   }
}
