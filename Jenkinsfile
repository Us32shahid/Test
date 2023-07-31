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
        
    post{
        success{
            emailext body: 'This Email sent out from Jenkins', subject: 'Test Notifications', to: 'us323619@gmail.com'
        }          
    }            
 }
}
