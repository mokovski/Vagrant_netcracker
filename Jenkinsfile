#!groovy
properties([disableConcurrentBuilds()])
pipeline {
    agent { 
        label 'master'
        }
    options {
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
        timestamps()
        }
    stages {
        stage("First step") {
            steps {
                sh 'ssh root@192.168.56.103 \'systemctl status sshd\''
            }
        }
        stage("Second step") {
            steps {
                sh 'ssh root@192.168.56.103 \'systemctl status httpd\''
            }
        }
        stage("3 step") {
            steps {
                sh 'ssh root@192.168.56.103 \'echo Web Server Apache Works\''
            }
        }    
    }
}
