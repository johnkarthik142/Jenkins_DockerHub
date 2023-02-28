pipeline {
  agent { label 'linux'}
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    DOKERHUB_CREDENTIALS_USR = credentials('johnkarthik142')
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t jenkins/dp-alpine:latest .'
       
      }
    }
    stage('Login') {
      steps {
       sh 'docker login -u $DOKERHUB_CREDENTIALS_USR --password-Looser@123'
    
      }
    }      
    stage('Push') {
      steps {
        sh 'docker push johnkarthik142/dp-alpine:latest'
        
      }
    }
   
    post {
     always {
      sh 'docker logout'
      }
   }
 }


}
