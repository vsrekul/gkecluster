pipeline {
    agent any
    environment {
        PROJECT_ID = 'deep-lore-403621'
        CLUSTER_NAME = 'gkejenkins'
        LOCATION = 'us-central1-a'
        CREDENTIALS_ID = 'gkesa'
    }
    stages {
        stage('Deploy to GKE') {
            steps{
                step([
                $class: 'KubernetesEngineBuilder',
                projectId: env.PROJECT_ID,
                clusterName: env.CLUSTER_NAME,
                location: env.LOCATION,
                manifestPattern: 'agent-build.yaml',
                credentialsId: env.CREDENTIALS_ID
                )
            }
        }
    }
}
