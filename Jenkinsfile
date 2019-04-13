pipeline {
    agent any
	
	 parameters {
            string(name: 'Version', defaultValue: '1.0.0', description: 'Version')
            
        }
		
    stages {
        stage('Build') {
            steps {
                bat 'java -version'
                bat 'gradle build -b /online-shop-backend'
			
            }
        }
       
		
	
    }
  
}