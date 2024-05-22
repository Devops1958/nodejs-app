pipeline{
    agent any

    stages{
        stage('Dep install'){
            agent { docker {image 'node:9.8.0'} } 
            steps{
                sh 'npm cache clean'
                sh 'cat /etc/os-release'
                
                
                sh 'npm install'
            }
        }
    }
}