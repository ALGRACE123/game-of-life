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
  stage ('code compile') {
    steps {
      sh 'mvn install'
    }
  }
  
   stage ('Artifact uploader') {
    steps {
      nexusPublisher nexusInstanceId: '12315', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: '/var/lib/jenkins/workspace/code/gameoflife-web/target/gameoflife.war']], mavenCoordinate: [artifactId: 'facebook', groupId: 'www.facebook.com', packaging: 'war', version: '$BUILD_ID']]]
    }
  }
  
 }
}
