node('mavenbuilds'){
    def mvnHome = tool name: 'maven360', type: 'maven'
    stage('checkout'){
        echo "downloading the source code"
        git credentialsId: 'githubaccount', url: 'https://github.com/ramharig/simple-java-maven-app.git'
        echo "successfully checkout"
    }
    stage('build'){
        echo "building the job now"
        sh "${mvnHome}:/bin/mvn clean package"

    }
}
