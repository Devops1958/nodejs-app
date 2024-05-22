pipeline{
    agent { docker { image 'node:14'
           args '-u root:root'}}
    stages{
      stage('Dep install'){ 
        steps{
         //   sh 'npm cache clean'
         //   sh 'sudo chown -R 995:993 "/.npm"'
            sh 'npm install'
        }
      } 
      stage('package'){
        steps{
            sh 'npm pack'
        }
      } 
    }
}