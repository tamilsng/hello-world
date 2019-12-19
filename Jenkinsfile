node{
   stage('SCM Checkout'){
     git 'https://github.com/tamilsng/hello-world.git'
   }
   stage('compile-package'){
     def mvnHome= tool name: 'maven', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
   }

}
