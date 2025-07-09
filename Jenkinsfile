pipeline {
    agent {
        docker {
            image 'docker:20.10.16'   // or any Docker-in-Docker image
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/moustafadimashkieh/devsecops-hello-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t hello-app .'
            }
        }
        stage('Push to Registry') {
            steps {
                echo 'Push skipped'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s-deployment.yaml'
            }
        }
    }
}
