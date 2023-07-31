pipeline {
    agent {
        label "master" // Use the master node as an agent
    }

    stages {
        stage('Build') {
            steps {
                sh 'mkdir -p build && cp index.html build/'  // Copy the index.html file to a build directory..
            }
        }
    }
    
post {
        always {
            // Archive the build artifacts for Jenkins
            archiveArtifacts artifacts: 'build/**', allowEmptyArchive: true
        }
        success {
            // Send a success email notification
            emailext (
                from: 'usama@ctoxi.com'
                to: 'us323619@gmail.com',
                subject: "Jenkins Job Succeeded: ${currentBuild.fullDisplayName}",
                body: '''Hi this email sent from Jenkins

Congratulations! Your Jenkins job "${currentBuild.fullDisplayName}" has succeeded.

Thanks,
Usama''',)
        }
    }
}
