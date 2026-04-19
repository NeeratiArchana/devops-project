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
	stage('Push to Docker Hub') {
            steps {
                sh '''
                echo "YOUR_DOCKER_PASSWORD" | docker login -u NeeratiArchana --password-stdin
                docker push neeratiarchana/myapp
                '''
            }
	}	
    }
}
