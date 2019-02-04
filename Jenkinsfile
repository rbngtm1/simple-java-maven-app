node('mavenbuilds'){
    def mvnHome = tool name: 'maven360', type: 'maven'
    stage('checkout'){
    echo "downloading the scm"
    git credentialsId: 'githubaccount', url: 'https://github.com/ramharig/simple-java-maven-app.git'
    }
    stage('executing test cases'){
        echo "test case is started"
        sh "${mvnHome}/bin/mvn clean test"
        archiveArtifacts allowEmptyArchive: true, artifacts: 'target/surefire-reports/*.xml'
        
    }
    stage('build'){
    echo "building the job now"
    sh "${mvnHome}/bin/mvn clean package"
        }
    stage('post build action'){
    echo "sending an email to user"
}
}
