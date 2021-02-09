timestamps {
    node(){
        stage("Trivy Scan"){
            sh 'trivy image --format json --output trivy-results.json debian:10.8'
                    
            recordIssues(
                enabledForFailure: true,
                tool: trivy(pattern: '*.json')
            )
        }
        
    }
}
