pipeline { 
  agent any
  tools {
     gradle 'Gradle-6'
  }
  stages{
    stage('clone repository') {
        steps { 
            git 'https://github.com/coduori/java-todo'
            input {
              'What is your name'
            }
        }
    
    }
    stage('Build project') {
        steps { 
            sh 'gradle build'
        }
    }
        stage('Testing Source code') {
      steps { 
        sh 'gradle test'
      }
    }
        stage('Run Project') {
      steps { 
        sh 'gradle run'
      }
        }
  }
}
