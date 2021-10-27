pipeline {
    agent any 
    stages {
        stage('Clone the repo') {
            steps {
                echo 'clone the repo'
                sh 'rm -rf webapp1'
                sh 'git clone https://github.com/redolence0103/webapp1.git'
            }
        }
        stage('push repo to remote host') {
            steps {
                echo 'connect to remote host and pull down the lasest version'
                sh 'ssh  atid@218.236.22.95 sudo git -C /var/www/html pull origin master'
            }
        }
        stage('check website is up') {
            steps {
                echo 'check website is up.'
                sh 'curl 218.236.22.95 | head -n 1'
            }
        }
    }
}
