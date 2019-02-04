node('mavenbuilds'){
    stage('checkout'){
        echo "downloading the source code"
        git credentialsId: 'githubaccount', url: 'https://github.com/ramharig/simple-java-maven-app.git'
        echo "successfully checkousst"
    }
}
