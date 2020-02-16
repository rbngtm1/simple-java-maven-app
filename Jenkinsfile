node('mavenbuilds'){
    def mvnHome
    def version
    mvnHome=tool 'maven-3.6.3'
    version='3.6.3'
    stage('checkout'){
        echo "downloading the source code"
        git credentialsId: 'githubaccount', url: 'https://github.com/ramharig/simple-java-maven-app.git'
        echo "successfully checkout"
    }
    stage('execute test case'){
        echo "executing test cases"
        sh "${mvnHome}/bin/mvn clean test"
        archiveArtifacts allowEmptyArchive: true, artifacts: 'target/surefire-reports*.xml'
        junit allowEmptyResults: true, testResults: 'target/surefire-reports*.xml'
    }
    stage('build'){
        echo "building the job now"
        sh "${mvnHome}/bin/mvn clean package"
    }
    stage('post build'){
        echo "email to the user about the build status"
    }

}
