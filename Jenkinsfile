
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
               sh 'mkdir -p build && cp index.html build/'  // Copy the index.html file to a build directory..
            }
        }
    }

    post {
        always {
            // Sending email notification using emailext plugin
            emailext body: "Hi - This is an automated email sent from Jenkins. Your build has completed.",
                     subject: "Jenkins Build Notification",
                     to: "kamranbutt2011@gmail.com"
        }
    }
}
