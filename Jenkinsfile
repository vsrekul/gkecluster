pipeline {
  agent {
    kubernetes {
      cloud "gcp"
      yamlFile "agent-build.yaml"
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
