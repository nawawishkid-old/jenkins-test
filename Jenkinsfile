pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Processing Build steps..."'
            }
        }
    	stage('Test') {
    		steps {
    			retry(3) {
    				sh 'echo "Processing Test steps... If this failed, let\'s retry it 3 times!"'
    			}
    		}
    	}
        stage('Deploy - Staging') {
        	steps {
        		sh 'echo "Processing staging deployment steps..."'
        	}
        }
        stage('Deploy - Preproduction') {
        	steps {
        		input "Are you sure you want to deploy this project?"
        	}
        }
        stage('Deploy - Production') {
        	steps {
        		sh 'echo "Processing production deployment steps...'
        	}
        }
    }
    post {
    	always {
    		echo 'Pipeline finished! Fail or success? I don\'t care :P'
    	}
    	success {
    		echo 'Software delpoyed!'
    	}
    	failure {
    		echo 'Failed!'
    	}
    	unstable {
    		echo 'Unstable!'
    	}
    	changed {
    		echo 'Pipeline has changed'
    	}
    }
}