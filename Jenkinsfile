pipeline {
    agent any

    stages {
        stage('Clone repo') {
            steps {
                git 'https://github.com/Amis97/shop.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t sima-shop .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker stop sima-shop || true'
                sh 'docker rm sima-shop || true'
                sh 'docker run -d --name sima-shop -p 5000:5000 sima-shop' 
            }
        }
    }
}