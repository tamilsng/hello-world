podTemplate(
    inheritFrom: "maven", 
    label: "myJenkins", 
    cloud: "openshift", 
    ) {

    node("myJenkins") {
        
        stage ('SCM checkout'){
            echo 'Checking out git repository'
            checkout scm
        }
    
        stage ('Maven build'){
            echo 'Building project'
            sh "mvn package"
        }

    }
}
