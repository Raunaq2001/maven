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
                withSonarQubeEnv("sonarqube-8.9.9") { 
                bat 'mvn sonar:sonar'
                }
            }
        }
    }
}
