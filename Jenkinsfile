pipeline {
    
    agent any 
    tools
	{
	    maven 'maven'
	}		

    stages {
        stage('Build') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
                sh 'java -jar target/my-app-1.0-SNAPSHOT.jar'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                    
                }
            }
        }
        
    }
}
