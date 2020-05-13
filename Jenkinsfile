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
                sh "oc policy add-role-to-user admin developer -n ${project}"
                sh "oc new-build -n ${project} --binary --name=${app} -l app=${app} || echo 'Build exists'"
            }
        }
        stage('--package--') {
            steps {
                sh "echo hi"
            }
        }
    }
}
