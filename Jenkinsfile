node {
    
	stage('Init') {
    	
		bat 'if exist C:\\LINUX\\setup rd /q /s C:\\LINUX\\setup'
		bat 'mkdir C:\\LINUX\\setup'
	}
		
    stage('Build') {
		docker {
		image 'mapping/buildlinux_trunk'
		args '-v C:\\LINUX\\setup:/home/setup'
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