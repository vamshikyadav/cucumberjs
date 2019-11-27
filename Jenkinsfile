#!/usr/bin/env groovy
properties([
    parameters ([
            //string(defaultValue: "TEST", description: 'What environment?', name: 'userFlag')
            choice( name: 'environment', choices: ['key-dev', 'key-qa'], description: 'What Environment?'),
            choice( name: 'featurefile', choices: ['testRemote', 'testSlow'], description: 'Select the Feature file'),
        ])
])

pipeline {
  agent any
    
  tools {nodejs "node"}

    
  stages {
    if (params.environment == 'key-dev'){
      stage('Install dependencies') {
          steps {
            echo "Install dependencies in key-dev"          
            bat 'npm install'
          }
        }
   
      stage('Test') {
        steps {
          echo "run in key-dev" 
          bat 'npm run'
        }
      }      

    }

     if (params.environment == 'key-qa'){
      stage('Install dependencies') {
          steps {
            echo "Install dependencies in key-qa"  
            echo "environment: ${params.featurefile}"        
           // bat 'npm install'
          }
        }
   
      stage('Test') {
        steps {
          echo "run in key-qa" 
         // bat 'npm run '
        }
      }     
     }
  }
}