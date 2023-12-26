pipeline {
  agent any
  stage('Deploy to GKE') {
    steps {
      container("gcloud-builder") {
        script {
            sh "kubectl apply -f agent-build.yaml"
          }
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
