pipeline { 
  agent any
  tools {
     gradle 'Gradle-6'
  }
  retries(4)
  stages{
    stage('clone repository') {
        input {
            message 'What is your name?'
            ok 'Submit'
            submitter 'user1,user2,user3'
            submitterParameter 'AUTHORISED_BY'
            parameters{
                    string(name:'username', defaultValue: 'user', description: 'Username of the user pressing Ok')
            }
        }
        steps { 
            git 'https://github.com/coduori/java-todo'
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
