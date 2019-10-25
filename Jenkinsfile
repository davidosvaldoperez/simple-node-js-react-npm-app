pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3004:3000' 
        }
    }
    environment {
        CI = 'true'
    }
    triggers {
        pollSCM('*/2 * * * *') 
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
                sh 'npm build'
            }
        }
        stage('Testear'){
            steps {
                sh 'npm test'
            }
        }
    }
}
