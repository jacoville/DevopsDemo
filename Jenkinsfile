pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage('Confirm') {
            steps {
                echo 'Just started a build as notified from a github\'s webhook'
            }
        }
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'gitlabhollman', url: 'https://gitlab.com/rahch1982/gs-spring-boot.git']]])
            }
        }
        stage ('Build') {
            steps {
                sh 'mvn -f complete/pom.xml install' 
            }
        }
        stage ('Test') {
            steps {
                sh 'mvn -f complete/pom.xml clean test' 
            }
            post {
                success {
                    junit 'complete/target/**/*.xml' 
                }
            }
        }
    }
}