#!/usr/bin/env groovy
/*properties{
    parameters {
            //string(defaultValue: "TEST", description: 'What environment?', name: 'userFlag')
            choice( name: 'region', choices: ['key-dev', 'key-qa'])
            choice( name: 'featurefile', choices: ['testRemote', 'testSlow'])
        }
}*/
def workspace;
def name;

pipeline {
  agent any
    
  tools {nodejs "node"}
    
  stages {
        
    stage('checkout') {
      checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/vamshikyadav/cucumberjs.git']]])
      workspace
    }
        
    stage('Install dependencies') {
      steps {
        name = "key-dev"
        echo "Static Code Analysis ${name}"  
        sh 'npm install'
      }
    }
     
    stage('Test') {
      steps {
         sh 'npm test'
      }
    }      
  }
}