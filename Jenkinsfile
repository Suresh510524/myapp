pipeline {
    agent any

    // stages {

    //     stage('Clone Code') {
    //         steps {
    //             git 'https://github.com/Suresh510524/git.git'
    //         }
    //     }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebapp .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop mywebapp || true'
                sh 'docker rm mywebapp || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5050:5050 --name mywebapp mywebapp'
            }
        }
    }
}
