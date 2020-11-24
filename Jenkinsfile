#!groovy
pipeline {
    agent any

    stages {
        steps {
            withMaven(maven : 'apache-maven-3.6.1') {
                bat'mvn clean compile'
            }
        }
    }
}
