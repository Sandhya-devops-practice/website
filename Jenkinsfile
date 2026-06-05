pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t sandhyadockerpractice/website:v1 .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push sandhyadockerpractice/website:v1'
            }
        }

        stage('Deploy Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
