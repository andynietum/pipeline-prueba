#!groovy

pipeline {
    agent any 

    stages {  
        stage('Example Build') {
            agent { docker 'maven:3.5.0-jdk-8-alpine' } 
            steps {
                echo 'Hello, Maven'
                sh 'mvn clean compile'
            }
	}
    }
}


