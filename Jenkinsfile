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
      archiveArtifacts '**/target/*.war'
      }
   }
  stage('Artifact upload') {
      steps {
    // nexusPublisher nexusInstanceId: '1234', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'target/helloworld.war']], mavenCoordinate: [artifactId: 'hello-world-servlet-example', groupId: 'com.geekcap.vmturbo', packaging: 'war', version: '$BUILD_NUMBER']]]
      nexusPublisher nexusInstanceId: '12315', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: '/var/lib/jenkins/workspace/GameOfLife/gameoflife-web/target/gameoflife.war']], mavenCoordinate: [artifactId: 'gameoflife', groupId: 'com.wakaleo.gameoflife', packaging: 'war', version: '$BUILD_ID']]]
	  }	 
 }
 }
}
