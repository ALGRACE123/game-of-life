pipeline {
 agent any
    tools {
     maven 'mymaven'
   }
 stages {
    stage ('code checkout'){
       steps {
        git 'https://github.com/prashanth-1993/game-of-life.git'
       }
    }
  stage ('Buildind the code'){
       steps {
        sh 'mvn  install'
       }
    }
  stage('Results') {
      steps {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts 'target/*.war'
      }
 }
}
