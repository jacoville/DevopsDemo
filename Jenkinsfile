#!/usr/bin/env groovy

pipeline {
    agent any

node {
    stage('Checkout') {
    }
    
    stage ('Build') {
            sh 'mvn clean deploy'
        }
    }
}
