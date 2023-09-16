pipeline { 
  agent any
  tools {
     gradle 'Gradle-6'
  }
  stages { 
    stage('clone repository') {
        steps { 
            git 'https://github.com/coduori/java-todo'
        }
    }
    stage('Build project') {
        steps { 
            sh 'gradle build'
        }
    }
        stage('Tests') {
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
