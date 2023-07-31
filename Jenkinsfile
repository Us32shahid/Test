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
    stage('Email Notification'){
       mail bcc: '', body: '''Hi this email sent from Jenkins

Thanks
usama''', cc: '', from: '', replyTo: '', subject: 'Jenkins job', to: 'us323619@gmail.com'
    }
}