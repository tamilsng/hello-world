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
                oc new-build -n ${project} --binary --name=${app} -l app=${app} || echo 'Build exists'
                oc start-build ${app} -n ${project} --from-dir=. --follow
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
