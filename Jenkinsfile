pipeline {
    agent any
   tools {
        maven 'maven-3'
    }
    stages {
        stage('Clean') {
            steps {
               cleanWs()
            }
        }
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/tolemi/szkolenie-ci-jenkins-example'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean verify'
            }
        }
    }
}
