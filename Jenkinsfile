#!groovy

pipeline {
    agent any 

    stages {  

	stage('Deploy') {
            agent { docker 'tomcat:8.0-java8' } 
	    sshagent(['Jenkins-Tomcat']) {
            	sh 'scp target/rest-0.0.1-SNAPSHOT.war 172.17.0.3:/usr/local/tomcat/webapps'
	   }
            steps {
                echo 'Hello, Tomcat'
            }
	}

    }
}


