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
            // Send email notification using SendGrid
            emailext (
                mail bcc: '', body: 'Hi, This is Email sent from Jenkins', cc: '', from: '', replyTo: '', subject: 'jenkins-job', to: 'us323619@gmail.com')
        }
    }
}