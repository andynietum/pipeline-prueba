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
      steps {
        sh '$JAVA_HOME/bin/java -cp    /home/andres/Oracle/Middleware/Oracle_Home/wlserver/server/lib/weblogic.jar weblogic.Deployer -adminurl t3://172.17.0.3:7001 -user weblogic -password 006a24c9 -deploy /home/andres/fluxit/redlink-servicios/hbcustom/pipelines/rest/target/rest-0.0.1-SNAPSHOT.war -remote -upload'
      }
    }
  }
  tools {
    jdk 'JDK-8u131'
  }
  environment {
    CLASSPATH = '/home/andres/Oracle/Middleware/Oracle_Home/wlserver/server/lib/weblogic.jar'
  }
}