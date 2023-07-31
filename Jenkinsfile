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
        stage('Email Notification') {
            mail bcc: '', body: '''This email sent from jenkins
            Thanks
            Jenkins''', cc: '', from: 'us323619@gmail.com', replyTo: '', subject: 'jenkins job', to: 'us323619@gmail.com'

            The build has completed.
                
    }
}


