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
       
		 stage('Test') {
            steps {
				bat 'cd online-shop-backend'
                bat 'gradle test'
            }
            post {
                always {
                    junit 'target\surefire-reports\*.xml'
                }
            }
        }
		 stage('Deploy') {
            steps {
                echo "Deploy ${params.Version}!"
            }
        }
	
    }
      post {
            always {
                junit 'build/reports/**/*.xml'
            }
        }
}