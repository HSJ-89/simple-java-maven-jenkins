pipeline {
    
    agent {
	    node {
	      label 'my-defined-label'
	      customWorkspace 'D:\HSJ\WorkSpace\maven'
	    }
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
