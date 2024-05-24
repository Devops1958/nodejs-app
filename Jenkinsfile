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
            sh 'rm -rf *.tgz || echo ""'
            sh 'npm pack'
        }
      } 
      stage( 'upload artifact'){
        steps{
            sh 'curl -uadmin:APAtrqGdCmQEVEvzSAvbZF6a9tv -T \
            *.tgz \
            "http://54.88.190.251:8081/artifactory/code-nodejs/file2-${BUILD_ID}.tgz"'
      }
    }
}
}