pipeline {
    agent any
   tools {
        maven 'maven-3'
    }
    stages {
        stage('Clean') {
//            when {
//                not {
//                    changelog '.*^\\[ci skip\\] .+$'
//                }
            }
            steps {
                scmSkip(deleteBuild: true, skipPattern:'.*\\[ci skip\\].*')
                cleanWs()
            }
        }
        stage('Checkout') {
//            when {
//                not {
//                    changelog '.*^\\[ci skip\\] .+$'
//                }
//            }
            steps {
                git branch: 'main', url: 'https://github.com/tolemi/szkolenie-ci-jenkins-example'
            }
        }
        stage('Build') {
//            when {
//                not {
//                    changelog '.*^\\[ci skip\\] .+$'
//                }
//            }
            steps {
                sh 'mvn clean verify'
            }
        }
    }
}
