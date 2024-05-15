pipeline {
    agent {
        docker { image 'node:20.11.1-alpine3.19' }
    }
    stages {
        stage('Build') { 
            steps {
                bat 'npm install' 
            }
        }
        stage('Deliver') { 
            steps {
                bat './jenkins/scripts/deliver.bat' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
                bat'./jenkins/scripts/kill.bat' 
            }
        }
    }
}