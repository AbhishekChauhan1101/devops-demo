pipeline {
    agent any

    stages {

        stage("Install Dependencies") {
            steps {
                sh 'npm ci'
            }
        }

        stage("Test") {
            steps {
                sh 'npm test'
            }
        }

        stage("Docker Build") {
            steps {
                sh 'docker build -t devops-demo:1.0 .'
            }
        }
        stage("Deploy to Kubernetes") {
    steps {
        sh 'kubectl apply -f deployment.yml'
        sh 'kubectl apply -f service.yml'
        sh 'kubectl rollout status deployment/devops-demo'
            }
        }
    }
}
