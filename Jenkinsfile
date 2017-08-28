#!groovy

pipeline {
    agent any 

    stages {  
        stage('Build') {
            agent { docker 'maven:3.5.0-jdk-8-alpine' } 
            steps {
                sh 'mvn clean install'
		archiveArtifacts artifacts: '**/target/*.war', fingerprint: true 
            }
	}
	stage('Deploy') {
            agent { docker 'tomcat:8.0-java8' } 
            steps {
                echo 'Hello, Tomcat'
		sshagent(['Jenkins-Tomcat']) {
	             scp target/rest-0.0.1-SNAPSHOT.war 172.17.0.3:/usr/local/tomcat/webapps
		}
            }
	}

    }
}


