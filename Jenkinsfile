
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t johnkarthik142/dp-alpine:latest .'
       
      }
    }
    stage('Login') {
      steps {
        sh 'echo $DOKERHUB_CREDENTIALS_PSW | docker login -u $DOKERHUB_CREDENTIALS_USR --password-stdin'
    
      }
    }      
    stage('Push') {
      steps {
        sh 'docker push johnkarthik142/dp-alpine:latest'
        
      }
    }
  }
  post{
    always {
      sh 'docker logout'
    }
  }

