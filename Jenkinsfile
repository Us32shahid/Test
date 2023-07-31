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
                // Send email notification after the build stage is completed
                emailext (
                    to: 'us323619@gmail.com',
                    subject: 'Jenkins Job',
                    body: '''This email sent from Jenkins

Thanks
Jenkins'''
                    // Additional options like bcc, cc, from, replyTo can be added if needed
                )
            }
        }
    }
}
