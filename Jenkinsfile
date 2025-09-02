pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
		echo "Starting build..."
		echo "BUILD_NUMBER: ${env.BUILD_NUMBER}"
                sh 'npm install'
		echo "Finished build!"
            }
        }
    }
}
