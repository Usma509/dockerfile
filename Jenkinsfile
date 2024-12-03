pipeline {
    agent any
    
    environment {
        // Set the environment variables
        dockerImage = ''  // Define the image variable (you can leave it empty for now)
        registry = 'usma001/pythonapp'  // The name of your Docker registry and image
    }
    
    stages {
        stage('Checkout') {
            steps {
                script {
                    // Manually clone the repository using Git
                    git url: 'https://github.com/Usma509/dockerfile.git', branch: 'main'
                }
            }
        }
        
        stage('Docker Build Image') {
            steps {
                script {
                    // Build the Docker image using the Dockerfile in the repository
                    dockerImage = docker.build("${registry}:latest")  // Build the Docker image with the 'latest' tag
                }
            }
        }
    }
}
