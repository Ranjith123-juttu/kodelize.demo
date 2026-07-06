pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Repository downloaded'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t student-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop student-app || true'
                sh 'docker rm student-app || true'
                sh 'docker run -d --name student-app -p 8080:80 student-app'
            }
        }
    }
}
