pipeline {
    agent {
        docker {
            image 'vsenxx/apache-php-git'
            args '-p 80:80 -u root -v "$PWD":/var/www/html'
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
