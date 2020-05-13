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
                sh '''#!/bin/bash
                oc policy add-role-to-user admin developer -n aub2
                oc new-build -n aub2 --binary --name=hello-world -l app=hello-world || echo Build exists
                oc start-build hello-world -n aub2 --from-dir=. --follow
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
