pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/NeeratiArchana/devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t neeratiarchana/myapp .'
            }
        }
    }
}
