pipeline {
    agent {
        label 'maven'
    }
    stages {
        stage('Maven Test and Package') {
            steps {
                sh "mvn clean install"
            }
        }
        stage('Build Image') {
            steps {
                sh "cp webapp/target/webapp.war target/ROOT.war"
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
