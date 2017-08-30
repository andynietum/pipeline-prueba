pipeline {
  agent any
  stages {
    stage('Deploy') {
      steps {
	env.JAVA_HOME="${tool 'JDK-8u131'}"
	env.PATH="${env.JAVA_HOME}/bin:${env.PATH}"
        sh 'sh java weblogic.Deployer -adminurl t3://172.17.0.3:7001 -user weblogic -password 006a24c9 -deploy /home/andres/fluxit/redlink-servicios/hbcustom/pipelines/rest/target/rest-0.0.1-SNAPSHOT.war -remote -upload'
      }
    }
  }
}