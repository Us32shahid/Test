pipeline {
    agent {
        label "master" // Use the master node as an agent
    }

    stages {
        stage('Build') {
            steps {
                // Clean the build directory before copying the index.html file
                sh 'rm -rf build'
                sh 'mkdir -p build'
                sh 'cp index.html build/'  // Copy the index.html file to the build directory.
            }
        }
    }

    post {
        always {
            // Archive the build artifacts for later use
            archiveArtifacts 'build/**'
        }
    }

    stage('Email Notification') {
        steps {
            // Send email notification after the build stage is completed
            emailext (
                to: 'us323619@gmail.com',
                subject: "Jenkins Job: ${currentBuild.fullDisplayName}",
                body: '''Hi,

The build of ${env.JOB_NAME} ${env.BUILD_NUMBER} has completed.

Thanks,
usama'''
                // Additional options like bcc, cc, from, replyTo can be added if needed
            )
        }
    }
}
