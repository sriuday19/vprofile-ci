pipeline {
    agent any

    tools {
        jdk "OracleJDK8"
        maven "MAVEN3"
    }

    stages {

        stage('fecth code') {

            steps {
                git branch:'main', url: 'https://github.com/sriuday19/vprofile-ci.git'
            }
        }

        stage('Build code') {

            steps {
                sh 'mvn clean install'
            } 

            post {
                success {
                    echo 'Archieving the artifact'
                    archiveArtifacts artifacts: "**/target/*.war"
                }
            }
        }

        stage('Test') {

            steps {
                sh 'mvn test'
            }
        }

        stage('Checkstyle Analysis') {

            steps {
                sh 'mvn checkstyle:checkstyle'
            }
        }
    }
}