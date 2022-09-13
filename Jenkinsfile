pipeline {
    agent any 
    stages {
        stage('Clone Repo and Clean Workspace') { 
            steps {
                bat "del /F /Q maven-app"
                bat "rmdir /S /Q maven-app"
                bat "git clone https://github.com/halifreaks/maven-app.git" 
                bat "mvn clean -f maven-app"
            }
        }
        stage('Test') { 
            steps {
                bat "mvn test -f maven-app"
            }
        }
        stage('Deploy') { 
            steps {
                bat "mvn package -f maven-app"            }
        }
    }
}