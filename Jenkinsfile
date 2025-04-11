pipeline {
    agent any
    tools {
        nodejs 'NodeJS 14' // Ensure this matches the name configured in Jenkins
    }
    environment {
        CI = 'true'
        NODE_OPTIONS = '--max-old-space-size=4096'
        GIT_SSL_NO_VERIFY = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'node -v'
                sh 'npm -v'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}