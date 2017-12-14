pipeline {
    agent {
        docker {
            image 'vsenxx/apache-php-git'
            args '-p 80:80'
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
