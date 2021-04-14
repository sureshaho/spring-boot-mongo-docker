pipeline {
    
    environment{
        PATH = "/opt/maven/apache-maven-3.8.1/bin:$PATH"
        
    }
    
    agent any
    stages{
        stage("Maven build"){
            steps{
                sh "mvn clean install package"
            }
        }
        stage("push to nexus"){
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'spring-boot-mongo', classifier: '', file: 'target/spring-boot-mongo-2.1.6.SNAPSHOT.jar', type: 'jar']], credentialsId: '233b403f-4f7c-4e9d-b683-cfdf439cdbcb', groupId: 'org.springframework.boot', nexusUrl: '172.20.10.217:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'suresha-SNAPSHOT', version: '2.1.6.SNAPSHOT'
            }
        }
    }  
}
