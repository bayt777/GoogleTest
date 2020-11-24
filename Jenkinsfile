#!groovy
pipeline {
    agent any

    stages {
        stage('Test') {
             steps{
                bat "git checkout main"
                bat "git config --global credential.helper store"
                bat "jx step git credentials"
                bat 'mvn clean compile'
            }
        }
    }
}
