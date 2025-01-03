pipeline {
    agent any
    tools {
        maven 'Maven 3.9.9' // Remplacez par le nom de votre installation Maven dans Jenkins
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install -DskipTests'
            }
        }
        stage('Run WebGoat') {
            steps {
                sh 'docker run -d -p 8080:8080 webgoat/webgoat'
            }
        }
    }
}
