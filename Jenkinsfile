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
        
        (emailext body: ''${FILE, path="$WORKSPACE/results/summary.txt"}'', subject: '${currentBuild.currentResult}: ${env.JOB_NAME} - build ${currentBuild.number}",', to: 'saad89.linux@gmail.com,us323619@gmail.com'
        )

        
    }
}

}        
    

