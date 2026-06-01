pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Code cloned successfully'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f mywebsite || true'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker run -d -p 80:80 --name mywebsite mywebsite'
            }
        }
    }
}
