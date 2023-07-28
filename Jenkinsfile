pipeline {
    agent {
        label "master" // Use the master node as an agent
    }

    stages {
        stage('Build') {
            steps {
                sh 'cp index.html build/'  // Copy the index.html file to a build directory
            }
        }
    }

    post {
        always {
            emailext body: "Code changes detected in the repository.", 
                    subject: "Build Notification - ${currentBuild.currentResult}", 
                    to: "your-email@example.com"
        }
    }
}