node {
    
	stage('Init') {
    	
		bat 'if exist C:\\TEST\\setup rd /q /s C:\\TEST\\setup'
		bat 'mkdir C:\\TEST\\setup'
	}
		
    stage('Build') {
		docker {
		image 'mapping/buildlinux_trunk'
		args '-v C:\\TEST\\setup:/home/setup'
		}    	
    }
    
    stage('Unit Test') {
    }
    
    stage('Integration Test') {
			
		
    }
	
	stage('Changelog') {
    }
    
    stage('Deploy') {
    }
	
}