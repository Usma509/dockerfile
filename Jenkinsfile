pipeline {
    agent any

    environment {
        dockerImage = ''  // Define the image variable
        registry = 'usma001/pythonapp'  // Your Docker registry and image name
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Usma509/dockerfile.git', branch: 'main'
            }
        }

        stage('Docker Build Image') {
            steps {
                script {
                    // Check if docker is available
                    if (isUnix()) {
                        dockerImage = docker.build("${registry}:latest")  // Build the Docker image with the 'latest' tag
                    } else {
                        echo "Docker not available on this machine"
                    }
                }
            }
        }
    }
}
