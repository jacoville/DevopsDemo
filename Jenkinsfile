pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {

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
