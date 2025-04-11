pipeline {
    agent any
    environment {
        CI = 'true'
        NODE_OPTIONS = '--max-old-space-size=4096'
        GIT_SSL_NO_VERIFY = 'true'
    }
    stages {
        stage('Build') {
            steps {
            withEnv(["PATH+NODE=/usr/local/bin"]) {
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
