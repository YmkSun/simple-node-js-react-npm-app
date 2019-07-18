pipeline {
    agent any
    environment {
		CI = 'true'
    }
    stages {
        stage('Build') { 
            steps {
                bat 'npm install' 
            }
        }
		stage('Test') { 
            steps {
                bat 'npm install --save-dev cross-env'
                bat 'npm test' 
            }
        }
	}
}