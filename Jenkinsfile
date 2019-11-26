#!/usr/bin/env groovy
properties{
    parameters {
            //string(defaultValue: "TEST", description: 'What environment?', name: 'userFlag')
            choice( name: 'region', choices: ['key-dev', 'key-qa'])
            choice( name: 'featurefile', choices: ['testRemote', 'testSlow'])
        }
}

pipeline {
    agent any
   
    stages {
        stage('Get Source') {
            checkout scm
        }
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
 }