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
        
        stage('Build'){
            steps{
              // git branch: 'main', changelog: false, poll: false, url: 'https://github.com/LoneLeveling/jenkins-hello-world.git'
                sh "mvn clean package -DskipTests=true"
            }
        }
     
     stage('Unit Test'){
         steps{
             script{
             for (int i=0;i<60;i++){
                 echo "${i+1}"
                 sleep 1
             }
             }
             sh "mvn test"
         }
     }
    }
}

