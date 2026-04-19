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
        	withCredentials([usernamePassword(
            	    credentialsId: 'docker-creds',
            	    usernameVariable: 'DOCKER_USER',
            	    passwordVariable: 'DOCKER_PASS'
        	)]) {
            	    sh '''
            	    echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
            	    docker push neeratiarchana/myapp
            	    '''
        	}
    	    }
	
        }
    }
}
