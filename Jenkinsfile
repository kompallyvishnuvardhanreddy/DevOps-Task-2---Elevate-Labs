pipeline {
    agent any
    stages {
        stage ("Code") {
            steps {
                git 'https://github.com/kompallyvishnuvardhanreddy/DevOps-Task-2---Elevate-Labs.git'
            }
        }
        stage ("Build") {
            steps {
                sh 'docker build -t image1 .'
            }
        }
        stage ("Test") {
            steps {
                echo "HTML site is valid - no automated tests configured."
            }
        }
        stage ("Deploy") {
            steps {
                sh 'docker stop con1 || true'
                sh 'docker rm cont1 || true'
                sh 'docker run -itd --name cont1 -p 1234:80 image1'
            }
        } 
    }
}
