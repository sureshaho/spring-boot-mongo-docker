pipeline {
    
    environment{
        PATH = "/opt/maven/apache-maven-3.8.1/bin:$PATH"
        
    }
    
    agent any
    stages{
        stage("Maven build"){
            steps{
                sh "mvn clean package"
            }
        }
    }  
}
