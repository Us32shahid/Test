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
        emailext (
            to: 'us323619@gmail.com',
            subject: "${currentBuild.currentResult}: ${env.JOB_NAME} - build ${currentBuild.number}",
            body: '${FILE, path="$WORKSPACE/results/summary.txt"}'
        )
    }
}

}        
    

