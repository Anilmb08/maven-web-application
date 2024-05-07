pipeline {
  agent any
  tools {
    maven 'maven' 
  }
   triggers {
  pollSCM '* * * * *'
}

  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('ExecuteSonarQubeReport'){
      steps{
        sh  'mvn clean sonar:sonar'
   }
   }
    stage('Build Docker Image'){
       steps{
	  sh ' docker build -t anilkumarc401/dockerpocjobs .'
	    }
            }
    stage('UploadArtifactsIntoNexus'){
       steps{
         sh  "mvn clean deploy"
                   }
                   }
                   }
}
