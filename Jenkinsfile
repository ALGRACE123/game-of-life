pipeline {
 agent any
     tools {
       maven 'Maven'
     }
     stages {
          stage('code checkout') {
               steps {
                  git 'https://github.com/prashanth-1993/game-of-life.git'
               }
           }
          stage('code Build') {
             steps {
                sh 'mvn package'
             }
          }
        stage('Unit Test Results') {
             steps {
                junit '**/target/surefire-reports/TEST-*.xml'
             }
          }
          
     }
}
