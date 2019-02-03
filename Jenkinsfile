node('mavenbuilds'){
    def mvnHome = tool name: 'maven360', type: 'maven'
    stage('checkout'){
    echo "downloading the scm"
    git credentialsId: 'githubaccount', url: 'https://github.com/ramharig/simple-java-maven-app.git'
    }
    stage('executing test cases'){
        echo "test case is started"
        sh "${mvnHome}/bin/mvn clean test"
    }
    stage('build'){
    echo "building the job now"
    sh "${mvnHome}/bin/mvn clean package"
    
    }
}
