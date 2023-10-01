pipeline {

  agent any
  
  stages {

    stage('Build') {
      // Build steps
    }

    stage('Build Docker Image') {
      // Docker build steps
    }

    stage('Push Docker Image') {
      // Docker push steps
    }

    stage('Deploy to Production') {
    
      steps {
      
        withCredentials([usernamePassword(credentialsId: 'webserver_login', usernameVariable: 'USERNAME', passwordVariable: 'USERPASS')]) {
        
          script {
          
            sh "ssh-keyscan ${env.prod_ip} >> ~/.ssh/known_hosts"
            
            sh "sshpass -p '$USERPASS' ssh $USERNAME@${env.prod_ip} 'docker pull...'"
            
            // Rest of SSH commands
            
          }
          
        }
        
      }
      
    }
  
  }

}
