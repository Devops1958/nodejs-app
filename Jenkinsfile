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
      stage( 'upload artifact'){
        steps{
            sh 'curl -uadmin:APAtrqGdCmQEVEvzSAvbZF6a9tv -T \
            *.tgz \ 
             "http://ec2-100-26-214-137.compute-1.amazonaws.com:8081/artifactory/utc-nodejs/utc-app-${BUILD_ID}.tgz"'
        }
      }
    }
}