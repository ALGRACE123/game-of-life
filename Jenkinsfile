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
       stage('Nexus Repository') {
             steps {
                nexusPublisher nexusInstanceId: '1234', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: '/var/lib/jenkins/workspace/GameOfLIfe/gameoflife-web/target/gameoflife.war']], mavenCoordinate: [artifactId: 'gameoflife', groupId: 'com.wakaleo.gameoflife', packaging: 'war', version: '$BUILD_NUMBER']]]
             }
          }
      
      
          
     }
}
