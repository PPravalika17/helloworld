pipeline{
  agent any
  stages{
    stage('compute'){
      steps{
        bat 'javac Factorial.java TestFactorial.java'
      }
    }
    stage('Test'){
      steps{
        bat 'java TestFactorial.java'
      }
    }
    stage('Run'){
      steps{
        bat 'java Factorial.java'
      }
    }
    stage('Package JAR'){
      steps{
        bat 'jar cfm Factorial.jar manifest.txt Factorial.class'
      }
    }
    stage('Archive JAR'){
      steps{
        archiveArtifacts artifacts:'Factorial.jar'
      }
    }
  }
    post{
      success{
        echo 'Build,test,run and JAR action successfuk and artifact ready'
      }
    
    failure{
      echo 'build failed'
    }
    }
}

    
