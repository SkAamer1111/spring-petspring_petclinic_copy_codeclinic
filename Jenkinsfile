pipeline{
    agent { label 'practice' }
    options {
        timeout(time: 30, unit: 'MINUTE')
    }
    triggers {
        pollSCM(* * * * *)
    }
    tools {
        jdk 'jdv_17',
        maven 'maven-3.9.3'
    }
    stages {
        stage('get code') {
            steps {
                git url: '',
                    branch: 'develop'

            }

        }
        stage('build and package') {
            steps {

            }
        }
        stage('report') {
            steps {

            }
        }
    }
}