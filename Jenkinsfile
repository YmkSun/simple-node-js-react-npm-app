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
	stage('Deliver') {
            steps {
                bat 'npm run build'
                bat 'npm start &'
                bat 'sleep 1'
                bat 'echo $! > .pidfile'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                bat 'kill $(cat .pidfile)'
            }
        }
    }
}