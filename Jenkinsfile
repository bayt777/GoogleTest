#!groovy

pipeline {
    agent {
        label "master"
    }
    stages {
        stage('Run tests') {
            when {
                branch 'master'
            }
            steps {
                container('maven') {
                    sh "git checkout master"
                    sh "git config --global credential.helper store"
                    sh "jx step git credentials"
                    sh 'mvn clean compile'
                }
            }
            post {
                always {
                    cleanWs()
                }
            }
        }
        stage('Build tests project') {
            when {
                not {
                    anyOf {
                        branch 'master'
                        branch 'PR-*'
                        branch 'Release-*'
                    }
                }
            }
            steps {
                container('maven') {
                    sh "git config --global credential.helper store"
                    sh "jx step git credentials"
                    sh 'mvn clean compile'
                }
            }
            post {
                always {
                    cleanWs()
                }
            }
        }
    }
}