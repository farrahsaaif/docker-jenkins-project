pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/farrahsaaif/docker-jenkins-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('fatima03')
                }
            }
        }

        stage('Push Docker Image to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'c5027272-a513-4734-aa5d-c3376a5e8bd5') {
                        docker.image('fatima03').push('latest')
                    }
                }
            }
        }

        stage('Pull Docker Image') {
            steps {
                script {
                    docker.image('your-docker-image-name:latest').pull()
                }
            }
        }
    }
}
