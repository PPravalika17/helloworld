pipeline{
  agent any
  stages{
    stage('compute'){
      steps{
        bat 'javac factorial.java TestFactorial.java'
      }
    }
    stage('Test'){
      steps{
        bat 'java TestFactorial.java'
      }
    }
    stage('Run'){
      steps{
        bat 'java factorial.java'
      }
    }
    stage('Package JAR'){
      steps{
        bat 'jar cfm factorial.jar manifest.txt factorial.class'
      }
    }
    stage('Archive JAR'){
      steps{
        archiveArtifacts artifacts:'factorial.jar'
      }
    }
  }
    post{
      success{
        echo 'Build,test,run and JAR action successfuk and artifact ready'
      }
    }
    failure{
      echo 'build failed'
    }
  
}

    
