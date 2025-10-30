pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 chandanayedelli/registration:v1'
                bat 'docker push chandanayedelli/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f D:/devops/Week-2/deployment.yaml'
                bat 'kubectl apply -f D:/devops/Week-2/service.yaml'
            }
        }
    }
}
