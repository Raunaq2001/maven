pipeline {
    agent any
    environment{
        PATH = "C:/Program Files/apache-maven-3.8.6/bin/mvn:$PATH"
    }
    stages {
        stage("build code") {
            steps{
                bat "mvn clean compile"
            }
        }
        stage("Test code") {
            steps{
                bat "mvn test"
            }
        }
        stage('SonarQube analysis') {
            steps{
                withSonarQubeEnv(credentialsId: 'f225455e-ea59-40fa-8af7-08176e86507a', installationName: 'My SonarQube Server') { // You can override the credential to be used
                bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
                }
            }
        }
    }
}
