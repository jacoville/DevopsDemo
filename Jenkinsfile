pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {

        stage ('Build') {
            steps {
                sh 'mvn -f initial/pom.xml install' 
            }
        }
        stage ('Test') {
            steps {
                sh 'mvn -f initial/pom.xml clean test' 
            }
            //post {
                //success {
                    //junit 'target/surefire-reports/**/*.xml' 
                //}
            //}
        }
    }
}
