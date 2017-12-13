pipeline {
    agent {
        docker {
            image 'php:7.0-apache'
            args '-p 80:80 -v "$PWD":/var/www/html'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Init') {
            steps {
                sh 'php -version'
            }
        }       
    }
}
