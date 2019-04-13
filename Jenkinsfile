pipeline {
    agent any
	
	 parameters {
            string(name: 'Version', defaultValue: '1.0.0', description: 'Version')
            
        }
		
    stages {
        stage('Build') {
            steps {
                bat 'java -version'
                bat 'cd online-shop-backend'
				bat 'gradle build'
            }
        }
       
		
	
    }
  
}