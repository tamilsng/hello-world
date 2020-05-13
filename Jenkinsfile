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
                sh '''#!/usr/bin/groovy
                oc policy add-role-to-user admin developer -n aub2
                oc new-build -n aub2 --binary --name=hello-world -l app=hello-world || echo Build exists
                '''
            }
        }
        stage('--package--') {
            steps {
                sh "echo hi"
            }
        }
    }
}
