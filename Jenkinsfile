pipeline {
  agent { label 'linux'}
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    DOKERHUB_CREDENTIALS = credentials('jenkins_dockerhub_JK')
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t johnkarthik142/images_docker:latest .'
       
      }
    }
    stage('Login') {
      steps {
       sh 'docker login -u $DOKERHUB_CREDENTIALS_USR --password-Looser@123'
    
      }
    }      
    stage('Push') {
      steps {
        sh 'docker push johnkarthik142/images_docker:latest'
        
      }
    }
   
   
 }


}
