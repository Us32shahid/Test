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
                subject: "Jenkins Build ${currentBuild.currentResult}",
                body: "The Jenkins build has ${currentBuild.currentResult}.",
                recipientProviders: [[$class: 'CulpritsRecipientProvider']],
                to: "us323619@gmail.com",
                from: "jenkins@example.com"
            )
        }
    }
}