node{

    stage("Checkout Source Code"){
        echo "Checkout Source Code"
        checkout scm
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
    stage('Config'){
        configFileProvider([configFile(fileId: "28aa9f49-c590-45e9-9fae-b92c78f6c453", variable: 'MAVEN_SETTINGS')]) {
        sh "mvn -s $MAVEN_SETTINGS -Preposilite"
        }
    }
}



