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
                    if (isUnix()) {
                        // Ensure Docker is available and then build the Docker image
                        try {
                            dockerImage = docker.build("${registry}:latest")  // Build the Docker image with the 'latest' tag
                        } catch (Exception e) {
                            echo "Docker build failed: ${e.getMessage()}"
                            currentBuild.result = 'FAILURE'
                        }
                    } else {
                        echo "Docker not available on this machine"
                    }
                }
            }
        }
    }
}

