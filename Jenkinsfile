pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'git https://github.com/karthikeya68/flask-devops-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f flask-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 80:80 --name flask-container flask-app'
            }
        }
    }
}
