pipeline {
    agent any

    tools {
        maven "MAVEN3"
    }

    stages {

        stage('fecth code') {

            steps {
                git branch:'main', url: 'https://github.com/sriuday19/vprofile-project.git'
            }
        }

        stage('Build code') {

            steps {
                sh 'mvn clean install'
            }
        }
    }
}