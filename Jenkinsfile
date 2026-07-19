pipeline {
  agent any
  stages {
    stage('Debug') {
      steps {
        sh 'which mvn'
        sh 'which java'
        sh 'echo $JAVA_HOME'
        sh 'echo $PATH'
      }
    }

    stage('Echo Version') {
      steps {
        sh 'echo Print Maven Version'
        sh 'mvn -version'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
      }
    }

    stage('Unit Test') {
      steps {
        script {
          for (int i=0;i<60;i++){
            echo "${i+1}"
            sleep 1
          }
        }

        sh 'mvn test'
        junit(testResults: 'target/surefire-reports/TEST-*.xml', keepProperties: true, keepTestNames: true)
      }
    }

  }
  tools {
    jdk 'JDK21'
    maven 'M3915'
  }
}