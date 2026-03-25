pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebapp_latest .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f mywebapp_latest || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5050:5050 --name mywebapp_latest mywebapp_latest'
            }
        }
    }
}
