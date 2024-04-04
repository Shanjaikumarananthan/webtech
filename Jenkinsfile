pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage ('Build') {
            steps {
                bat 'mvn clean -Dmaven.test.skip package'
            } 
        }
        stage ('Run JAR File') {
            steps {
                script {
                    def jarFilePath = 'C:/ProgramData/Jenkins/.jenkins/workspace/demo3/target/sprinboot-restapi-0.0.1-SNAPSHOT.jar'
                    def batchScript = "cmd /c \"java -jar ${jarFilePath}\""
                    bat label: 'Run JAR in Background', script: batchScript
                }
            }
        }
    }
  
}
