pipeline {
    agent none
	
	stages {
		stage('Init') {			
			steps {
				echo "Init..."
				//bat 'if exist C:\\TEST\\setup rd /q /s C:\\TEST\\setup'
				//bat 'mkdir C:\\TEST\\setup'
			}
		}
			
		stage('Build') {
			agent {
				docker {
						image 'mapping/buildlinux_trunk'
						args '-v C:\\TEST\\setup:/home/setup'
				}	    
			}

			steps {
				echo "Build..."
			}			
		}
		
		stage('Unit Test') {
			steps {
				echo "Unit Test..."
			}
		}
		
		stage('Integration Test') {
			steps {
				echo "Integration Test..."
			}
				
			
		}
		
		stage('Changelog') {
			steps {
				echo "Changelog..."
			}
		}
		
		stage('Deploy') {
			steps {
				echo "Deploy..."
			}
		}
	}
	
}