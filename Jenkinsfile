pipeline {
    agent {
       docker {
          image 'maven:3-alpine'
          args  '-v ~/build:~/build -v ~/.m3 ~/.m3'
       }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
               echo 'Build phase'
               sleep 5
            }
        }
        stage('Test') {
            steps {
                echo 'Test phase'
                sleep 5
            }
        }
        stage('Deliver for development') {
            when {
                branch 'development'
            }
            steps {
               echo 'Delivers on development environment'
               sleep 5
            }
        }
        stage('Deploy for production') {
            when {
                branch 'production'
            }
            steps {
               echo 'Delivers on production environment'
               sleep 5
            }
        }
    }
}
