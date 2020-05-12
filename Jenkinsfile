pipeline {
    agent any
    stages {
        stage('Maven Test and Package') {
            steps {
                sh "mvn clean install"
            }
        }
        stage('--test--') {
            steps {
                sh "echo hi"
            }
        }
        stage('--package--') {
            steps {
                sh "echo hi hi"
            }
        }
    }
}