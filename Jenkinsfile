library(
  identifier: 'redhat-helloworld-msa/jenkins-library@master',
  retriever: modernSCM(
    [
      $class: 'GitSCMSource',
      remote: 'https://github.com/redhat-helloworld-msa/jenkins-library.git'
    ]
  )
)

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
                buildApp('cicd', 'hello-world')
                echo "This is the build number: ${env.BUILD_NUMBER}"
            }
        }
        stage('--package--') {
            steps {
                sh "echo hi hi"
            }
        }
    }
}
