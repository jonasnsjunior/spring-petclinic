pipeline {
  agent {
    docker {
      image 'openjdk:8-jre'
      args '-e teste \\"java .jar spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar"'
    }

  }
  stages {
    stage('Java') {
      steps {
        sh 'echo $JAVA_HOME'
        sh './mvnw verify'
      }
    }
    stage('run') {
      steps {
        sh './mvnw spring-boot:run'
      }
    }
  }
}