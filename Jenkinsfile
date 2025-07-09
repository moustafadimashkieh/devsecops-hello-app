pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/moustafadimashkieh/devsecops-hello-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('hello-app')
                }
            }
        }
        stage('Push to Registry') {
            steps {
                echo 'Push skipped (use DockerHub if needed)'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s-deployment.yaml'
            }
        }
    }
}