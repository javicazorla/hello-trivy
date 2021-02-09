pipeline {
    agent any
    stages {
        stage("Trivy Scan"){
            steps{
                sh 'trivy image --format json --output trivy-results.json debian:10.8'
            }
            post {
                always {
                    recordIssues(
                    enabledForFailure: true,
                    tool: trivy(pattern: '*.json')
                    )
                }
            }
        }
   
    }
}
