pipeline {
    agent {
        docker {
            image 'vsenxx/apache-php-git'
            args '--user root -p 80:80 -v /var/run/docker.sock:/var/run/docker.sock -v "$PWD":/var/www/html'
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
