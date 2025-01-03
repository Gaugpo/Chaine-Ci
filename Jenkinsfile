pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Exécute Maven pour construire l'application
                    sh 'mvn clean install -DskipTests'
                }
            }
        }
        stage('Run WebGoat') {
            steps {
                script {
                    // Commande pour démarrer WebGoat, ajustez selon votre configuration
                    sh 'docker run -d -p 8080:8080 webgoat/webgoat'
                }
            }
        }
    }
}
