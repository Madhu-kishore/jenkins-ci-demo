pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Madhu-kishore/jenkins-ci-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t abhinava533289/hello-jenkins:latest .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push abhinava533289/hello-jenkins:latest'
            }
        }
    }
}
