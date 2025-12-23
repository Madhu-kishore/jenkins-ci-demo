pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Madhu-kishore/jenkins-ci-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t abhinava533289/hello-jenkins:latest .'
            }
        }

        stage('Push Docker Image') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh '''
                        echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
                        docker push abhinava533289/hello-jenkins:latest
                    '''
                }
            }
        }
    }
}


