pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -p 5000:5000' 
        }
    }
    environment {
        CI = 'true'
        VAULT_ADDR ='http://127.0.0.1:8200'
        VAULT_TOKEN = 'hvs.EGs0PmHasKTB5WPc3pqhvzSo'
    }
    stages {
        stage('Build') {
            steps {
                sh 'ls'
                sh 'env'
                sh 'vault status'
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
