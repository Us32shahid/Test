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
        success {

            emailext (
                from: 'usama@ctoxi.com'
                to: 'us323619@gmail.com',
                subject: 'Test Notifications - Build Successful',
                body: '''Hi, 



Thanks,
Jenkins'''
                // Additional options like bcc, cc, from, replyTo can be added if needed
            )
        }
    }
}
