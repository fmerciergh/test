pipeline {
    agent none
	
	stages {
		stage('Init') {	

			agent any

			steps {
				echo "Init..."
				sh 'rm -rf $HOME/setup'
				sh 'mkdir $HOME/setup'
				sh 'rm -rf $HOME/src'
				sh 'svn checkout -q --non-interactive --username exploit --password VsS3o2s8 svn://192.168.216.21/mappingsuite/M-Suite/trunk $HOME/src'
				sh 'chmod 777 $HOME/src/compil/linux/make_build.sh'
			}
		}
			
		stage('Build') {
			agent {
				docker {
						image 'execut/mappingtest'
						registryUrl 'https://registry.hub.docker.com'
						registryCredentialsId 'docker_login'
						args '-v $HOME/setup:/home/setup -v $HOME/src:/home/src'
				}	    
			}

			steps {
				echo "Build..."
				sh 'cd /home/src/compil/linux && \
					./make_build.sh'
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