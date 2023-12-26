pipeline {
  agent any
  stage('Deploy to GKE') {
    steps {
      
        script {
             kubernetesDeploy(configs: "agent-build.yaml")
          }
        
      }
    } 
  }
  post {
    always {
      // Clean up the agent pod after the job completes
      cleanWs()
      deleteDir()
    }
  }
}
