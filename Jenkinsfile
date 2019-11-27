#!/usr/bin/env groovy
properties([
    parameters ([
            //string(defaultValue: "TEST", description: 'What environment?', name: 'userFlag')
            choice( name: 'environment', choices: ['key-dev', 'key-qa'], description: 'What Environment?'),
            choice( name: 'featurefile', choices: ['testRemote', 'testSlow'], description: 'Select the Feature file'),
        ])
])

  agent any
    
  tools {nodejs "node"}

    
  stages {
      // have to include the details of the environment
      stage("Environment Setup"){
      
            if (params.environment == 'key-dev'){          
            echo "you selected ${params.environment}"
            }
            if (params.environment == 'key-qa'){
              echo "you selected ${params.environment}"

            }

        
      }
      stage('Install dependencies') {
          
            echo "Install dependencies in key-dev"          
            bat 'npm install'
          
        }
   
      stage('Testing the feature file') {
        
          echo "running the feature file selected ${params.featurefile}" 
          bat "npm run ${params.featurefile}"
    
      }  
  }