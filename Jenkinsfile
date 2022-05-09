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
    configFileProvider([configFile(fileId: id_config, variable: 'MAVEN_SETTINGS')]) {
    sh "mvn -s $MAVEN_SETTINGS -Preposilite"
    }
}



