#!/usr/bin/env groovy
properties([
    parameters ([
            //string(defaultValue: "TEST", description: 'What environment?', name: 'userFlag')
            choice( name: 'region', choices: ['key-dev', 'key-qa'])
            choice( name: 'featurefile', choices: ['testRemote', 'testSlow'])
        ])
])

pipeline {
  agent any
    
  tools {nodejs "node"}

    
  stages {
    stage('Install dependencies') {
      steps {
        echo "Install dependencies"          
        bat 'npm install'
      }
    }
   
    stage('Test') {
      steps {
         echo "nps run" 
         bat 'npm run'
      }
    }      
  }
}