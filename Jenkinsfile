pipeline {
    
    agent any {
	    
	  }
	

    stages {
        stage('Build') {
            steps {
                bat 'mvn package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        
    }
}
