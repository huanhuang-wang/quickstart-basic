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
                sh 'php -r "readfile(\'https://getcomposer.org/installer\');" | php'
                sh 'ls'
            }
        }   
        stage('Test') {
            steps {
                sh 'php composer.phar'
            }
        }
    }
}
