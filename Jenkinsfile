pipeline{
    agent { label 'practice' }
    options {
        timeout(time: 30, unit: 'MINUTES')
    }
    triggers {
        pollSCM('* * * * *')
    }
    tools {
        jdk 'jdv_17',
        maven 'maven-3.9.3'
    }
    stages {
        stage('get code') {
            steps {
                git url: 'https://github.com/SkAamer1111/spring-petspring_petclinic_copy_codeclinic.git',
                    branch: 'develop'

            }

        }
        stage('build and package') {
            steps {
                sh script: 'mvn package'

            }
        }
        stage('report') {
            steps {
                archiveArtifacts artifacts: '**/spring-petclinic-*.jar'
                junit testResults: '**/surefire-reports/TEST-*.xml'

            }
        }
    }
}