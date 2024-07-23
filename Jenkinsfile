pipeline {
    agent any

    environment {
        DOCKER_CREDENTIALS_ID = 'vamshi0007gangamma'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Vamshiii2/abadevops.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t vamshi0007gangamma/helloworldapp:latest .'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry([credentialsId: "${DOCKER_CREDENTIALS_ID}", url: 'https://index.docker.io/v1/']) {
                        sh 'docker push vamshi0007gangamma/helloworldapp:latest'
                    }
                }
            }
        }
    }
}
