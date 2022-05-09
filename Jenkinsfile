node{
    stage('Build') {
        checkout SCM
    }
    stage('Test'){
       sh "mvn test"
    }
    stage('Package'){
        sh "mvn package -DskipTests"
    }
    stage('Upload'){
        sh "mvn deploy"
    }
}



