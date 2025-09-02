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
        stage('Test') {
            steps {
		echo "Starting test..."
                sh './jenkins/scripts/test.sh'
		echo "Finished test!"
            }
        }
        stage('Deliver') {
            steps {
		echo "Starting deliver..."
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
		echo "Finished deliver!"
            }
        }
    }
}
