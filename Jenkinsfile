pipeline {
    agent any
	
	 parameters {
            string(name: 'Greeting', defaultValue: 'Jenkins', description: 'Jenkins')
            
        }
		
    stages {
        stage('Build') {
            steps {
                bat 'java -version'
                bat './online-shop-backend/gradle build '
            }
        }
       
		 stage('Test') {
            steps {
                bat './online-shop-backend/gradle test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
		 stage('Deploy') {
            steps {
                echo "Deploy ${params.Greeting}!"
            }
        }
	
    }
      post {
            always {
                junit 'build/reports/**/*.xml'
            }
        }
}