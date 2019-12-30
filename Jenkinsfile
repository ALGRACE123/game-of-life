pipeline {
    agent any 
    tools { 
        maven 'Maven' 
      
    }
stages { 
     
 stage('Preparation') { 
     steps {
// for display purpose

      // Get some code from a GitHub repository

      git 'https://github.com/prashanth-1993/game-of-life.git'

      // Get the Maven tool.
     
 // ** NOTE: This 'M3' Maven tool must be configured
 
     // **       in the global configuration.   
     }
   }

   stage('Build') {
       steps {
       // Run the maven build

      //if (isUnix()) {
         sh 'mvn -Dmaven.test.failure.ignore=true install'
      //} 
      //else {
      //   bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
       }
//}
   }
 }
}
 

