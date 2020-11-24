#!groovy
pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh "git checkout master"
                sh "git config --global credential.helper store"
                sh "jx step git credentials"
                sh 'mvn clean test'
            }
        }
    }
}
