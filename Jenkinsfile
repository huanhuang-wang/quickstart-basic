pipeline {
    agent {
        docker {
            image 'php:5.6-apache'
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
                sh 'ls'
            }
        }   
        stage('Install') {
            steps {
                sh 'php composer.phar install'
            }
        }
    }
}
