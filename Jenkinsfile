pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
                docker {
                    image 'maven:3.9.3-eclipse-temurin-17'
                    args '-v $HOME/.m2:/root/.m2'
                }
            }
            steps {
                checkout scm // This line checks out the source code from your Git repository
                sh 'mvn --version'
                sh 'mvn clean'
                sh 'mvn test'
                
            }
        }
        stage('Front-end') {
            agent {
                docker {
                    image 'node:16-alpine'
                }
            }
            steps {
                sh 'node --version'
                // Add Front-end build steps here if needed
            }
        }
    }
}
