#!groovy

pipeline {
    agent any 

    stages {  

	stage('Deploy') {
            agent { docker 'tomcat:8.0-java8' } 
            steps {
                echo 'Hello, Tomcat'
            	sh 'scp target/rest-0.0.1-SNAPSHOT.war jenkins@172.17.0.3:/usr/local/tomcat/webapps'
	   
            }
	}

    }
}


