pipeline {
  agent any
  stages {
    stage('Deploy') {
      steps {
        sh '\'printenv\''
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