#!groovy

pipeline {
    agent any 

    stages {  

	stage ('Deploy'){
	    node{
		steps{
			echo ${env.WORKSPACE}
			sh 'curl --upload-file target/debug.war "http://tomcat:pass1234@172.16.1.3:8080/manager/deploy?path=/debug&update=true"'		
		}	
	    }		
	}

    }
}


