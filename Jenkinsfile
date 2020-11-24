#!groovy
pipeline {
    agent any

    stages {
        steps {
                bat "git checkout master"
                bat "git config --global credential.helper store"
                bat "jx step git credentials"
                bat 'mvn clean compile'
            }
        }
    }
}
