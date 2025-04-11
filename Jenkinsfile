pipeline {
    agent any
    environment {
        CI = 'true'
    withEnv(["PATH+NODE=/usr/local/bin"]) {
    sh 'node -v'
    sh 'npm -v'
    }
    stages {
        stage('Build') {
            steps {
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
