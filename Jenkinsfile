pipeline {
    agent {
        docker {
            image 'node:24-alpine3.21'
            args '-p 3000:3000 -p 5000:5000' 
            args '-v /.npm/:/.npm/'
        }
    }
    environment {
        CI = 'true'
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
