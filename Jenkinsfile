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
    
}



