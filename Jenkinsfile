pipeline {
    agent any
   tools {
        maven 'maven-3'
    }
    stages {
       when {
            not {
                changelog '.*^\\[ci skip\\] .+$'
            }
        }
        stage('Clean') {
            steps {
               cleanWs()
            }
        }
        when {
            not {
                changelog '.*^\\[ci skip\\] .+$'
            }
        }
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/tolemi/szkolenie-ci-jenkins-example'
            }
        }
        when {
            not {
                changelog '.*^\\[ci skip\\] .+$'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean verify'
            }
        }
    }
}
