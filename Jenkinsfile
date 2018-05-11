pipeline {
    agent { docker { image 'php' } }
    stages {
    	stage('my-stage') {
    		steps {
    			retry(3) {
    				sh 'echo This is my-stage stage! Let's retry it 3 times!'
    			}
    		}
    	}
        stage('build') {
            steps {
                sh 'php --version'
            }
        }
    }
    post {
    	always {
    		echo 'Pipeline finished! Fail or success? I don\'t care :P'
    	}
    	success {
    		echo 'Pipeline successed'
    	}
    	failure {
    		echo 'Pipeline failed'
    	}
    	unstable {
    		echo 'Unstable!'
    	}
    	changed {
    		echo 'Pipeline has changed'
    	}
    }
}