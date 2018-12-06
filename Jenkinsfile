pipeline {
    agent none
	
	stages {
		stage('Init') {	

			agent any

			steps {
				echo "Init..."
				bat 'if exist C:\\TEST\\setup rd /q /s C:\\TEST\\setup'
				bat 'mkdir C:\\TEST\\setup'
			}
		}
			
		stage('Build') {
			agent {
				docker {
						image 'mappingtest'
						registryUrl 'https://registry.hub.docker.com'
						registryCredentialsId 'docker_login'
						args '-v C:\\TEST\\setup:/home/setup'
				}	    
			}

			steps {
				echo "Build..."
				//bat 'svn checkout -q --non-interactive --username exploit --password VsS3o2s8 svn://192.168.216.21/mappingsuite/M-Suite/trunk /home/src && \
				//	cd /home/src/compil/linux && \
				//	chmod 777 make_build.sh && \
				//	./make_build.sh'
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