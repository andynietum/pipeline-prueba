#!groovy

pipeline {
    agent any 

    stages {  

	stage('Deploy') {
            agent { docker 'tomcat:8.0-java8' } 
            steps {
                echo 'Hello, Tomcat'
            	sh 'ls'
	   
            }
	}

    }
}


