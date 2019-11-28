#!/usr/bin/env groovy

properties([
    buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '10')),
    disableConcurrentBuilds()
])

node {
    stage('Checkout') {
    }
    
    stage ('Build') {
        withMaven(globalMavenSettingsConfig: "pom.xml", maven: "maven") {
            sh 'mvn clean deploy'
        }
    }
}
