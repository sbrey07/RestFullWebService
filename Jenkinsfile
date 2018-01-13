pipeline {
    agent {
       docker {
          image 'maven:alpine'
          args  '-v ~/build:~/build -v ~/.m3 ~/.m3'
       }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
               sh 'echo Build phase'
               sh 'sleep 5'
            }
        }
        stage('Test') {
            steps {
                sh 'echo Test phase'
                sh 'sleep 5'
            }
        }
        stage('Deliver for development') {
            when {
                branch 'development'
            }
            steps {
               sh 'echo Delivers on development environment'
               sh 'sleep 5'
            }
        }
        stage('Deploy for production') {
            when {
                branch 'production'
            }
            steps {
               sh 'echo Delivers on production environment'
               sh 'sleep 5'
            }
        }
    }
}
