pipeline {
    agent any
tools{
    jdk "JDK21"
    maven "M3915"
}
    stages {
        
       stage('Debug') {
    steps {
        sh 'which mvn'
        sh 'which java'
        sh 'echo $JAVA_HOME'
        sh 'echo $PATH'
          }
       }
        stage('Echo Version'){
            steps{
                sh 'echo Print Maven Version'
                sh 'mvn -version'
            }
        }
        
        stage('build'){
            steps{
              // git branch: 'main', changelog: false, poll: false, url: 'https://github.com/LoneLeveling/jenkins-hello-world.git'
                sh "mvn clean package -DskipTests=true"
            }
        }
     
     stage('Unit Test'){
         steps{
             sh "mvn test"
         }
     }
    }
}

