#!/usr/bin.env groovy

pipeline {   
    agent any
    stages {
        stage("test") {
            steps {
                script {
                    echo "Testing the application..."

                }
            }
        }
        stage("build") {
            steps {
                script {
                    echo "Building the application..."
                }
            }
        }

        stage("deploy") {
            steps {
                script {
                    def dockerCmd = 'docker run -p 3000:3000 -d c0ntrl08/module8-java-maven-app-for-dockerinjenkins:jma-1.0'
                    sshagent(['ec2-server-key']) {
                      sh "ssh -o StrictHostKeyChecking=no ec2-user@3.68.219.93 ${dockerCmd}"
                    }
                }
            }
        }               
    }
} 
