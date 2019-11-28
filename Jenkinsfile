#!/usr/bin/env groovy

pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3'
    }

node {
    stage('Checkout') {
    }
    
    stage ('Build') {
            sh 'mvn clean deploy'
        }
    }
}
