pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/example/zypher-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t zypher-app:v1 .'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push yourdockerhub/zypher-app:v1'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }

    }
}
