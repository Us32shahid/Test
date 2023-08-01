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
        
        (emailext body: '''Hi - This email sent out form Jenkins.
Thanks Jenkins''', subject: 'jenkins test email', to: 'us323619@gmail.com'
        )

        
    }
}

}        
    

