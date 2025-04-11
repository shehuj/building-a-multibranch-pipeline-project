pipeline {
    agent any
    environment {
        CI = 'true'
        NODE_OPTIONS = '--max-old-space-size=4096'
        GIT_SSL_NO_VERIFY = 'true'
    }
    tools {
        nodejs 'NodeJS 14' // Name of the NodeJS installation configured in Jenkins
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