pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3004:3000' 
        }
    }
    triggers {
        pollSCM('*/2 * * * *') 
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}
