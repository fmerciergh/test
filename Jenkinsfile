pipeline {
    agent none
	
	stages {
		stage('Init') {	

			agent any

			steps {
				echo "Init..."
				sh 'rm -rf $WORKSPACE/setup'
				sh 'mkdir $WORKSPACE/setup'
				sh 'rm -rf $WORKSPACE/src'
				sh 'svn checkout -q --non-interactive --username exploit --password VsS3o2s8 svn://192.168.216.21/mappingsuite/M-Suite/trunk $WORKSPACE/src'
				sh 'chmod 777 $WORKSPACE/src/compil/linux/make_build.sh'
			}
		}
			
		stage('Build Setup') {
			agent {
				docker {
						image 'execut/mappingtest'
						registryUrl 'https://registry.hub.docker.com'
						registryCredentialsId 'docker_login'
						args '-v $WORKSPACE/setup:/home/setup -v $WORKSPACE/src:/home/src'
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
		
		stage('Integration Test : Generation maquette') {
			steps {
				echo "Generation maquette..."
			}
		}
		
		stage('Integration Test : Generation report') {
			steps {
				echo "Generation report..."
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
		
			agent any
			
			steps {
				echo "Deploy..."
				sh 'cp $WORKSPACE/setup/* /home/jenkins/setups/'
			}
		}
	}
	
}