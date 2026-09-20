```groovy
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
    }
}
```
