#!groovy

pipeline {
    agent any 

    stages {  

	stage ('Deploy'){
	    agent{ label 'Una etiqueta'}
	    steps {
		echo ${env.WORKSPACE}
		sh 'curl --upload-file target/debug.war "http://tomcat:pass1234@172.16.1.3:8080/manager/deploy?path=/debug&update=true"'		
	    }
	}

    }
}


