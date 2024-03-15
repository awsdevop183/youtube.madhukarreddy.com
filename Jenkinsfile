pipeline {
    agent any

    stages {
        stage('Create Docker image') {
            steps {
                sh 'docker build -t youtube:v1 .'
            }
        }
        stage('Deleting old container') {
            steps {
                sh 'docker rm -f youtube'
            }
        } 
        stage('Create a container') {
            steps {
                sh 'docker run -d --name youtube -p 98:80 youtube:v1'
            }
        }
        stage('Dangling Image remove') {
            steps {
                sh 'docker image prune -f'
            }
        }

        
    }
}