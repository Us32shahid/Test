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

        stage('Email Notification') {
            steps {
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
}
