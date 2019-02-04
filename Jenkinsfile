node('mavenbuilds'){
    def mvnHome = tool name: 'maven360', type: 'maven'
    stage('checkout'){
        echo "downloading the source code"
        git credentialsId: 'githubaccount', url: 'https://github.com/ramharig/simple-java-maven-app.git'
        echo "successfully checkout"
    }
    stage('execute test case'){
        echo "executing test cases"
        sh "${mvnHome}/bin/mvn clean test"
        archiveArtifacts 'target/surefire-reports*.xml'
    }
    stage('build'){
        echo "building the job now"
        sh "${mvnHome}/bin/mvn clean package"
    }

}
