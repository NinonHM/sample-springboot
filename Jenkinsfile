node{

    stage("Checkout Source Code"){
        echo "Checkout Source Code"
        checkout scm
    }
    stage("Run unit tests"){
       sh "mvn test"
    }
    stage("Build artifact"){
        sh "mvn package -DskipTests"
    }
    stage("Deploy"){
        sh "mvn deploy"
    }
    stage("configFileProvider"){
        configFileProvider([configFile(fileId: "28aa9f49-c590-45e9-9fae-b92c78f6c453", variable: 'MAVEN_SETTINGS')]) {
        sh "mvn -s $MAVEN_SETTINGS -Preposilite"
        }
    }
}



