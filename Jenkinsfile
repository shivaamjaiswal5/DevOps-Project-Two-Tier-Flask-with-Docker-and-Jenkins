pipeline{
    agent any
    stages{
        stage('Clone Repository'){
            steps{
                git branch: 'main', url: 'https://github.com/shivaamjaiswal5/DevOps-Project-Two-Tier-Flask-with-Docker-and-Jenkins.git'
            }
        }
        stage('Build Docker Image'){
            steps{
                sh 'docker build -t flask-app .'
            }
        }
        stage('Deploy with Docker Compose'){
            steps{
                //exiting container if they are running
                sh 'docker compose down || true'
                //start app, rebuilding flask image
                sh 'docker compose up -d --build'
            }
        }
    }
}
