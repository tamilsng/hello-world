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
                sh "cp webapp/target/webapp.war ./webapp.war"
                script {
                    openshift.withCluster() {
                        openshift.withProject(env.aub2) {
                            openshift.selector("bc", "tasks").startBuild("--from-file=./webapp.war", "--wait=true")
                        }
                    }
                }
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
