pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebapp .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f mywebapp || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5050:5050 --name mywebapp mywebapp'
            }
        }
    }
}
