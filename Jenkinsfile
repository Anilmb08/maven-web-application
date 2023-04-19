pipeline {
  agent any
    agent { dockerfile true }	
  tools {
    maven 'maven' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('ExecuteSonarQubeReport'){
      steps{
        sh  "mvn clean sonar:sonar"
   }
   }	  
	  
	  
  }
}
