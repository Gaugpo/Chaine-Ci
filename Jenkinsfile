pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Récupérer le code depuis le dépôt Git
                git 'https://votre-depot-git.git'
            }
        }

        stage('SCA Analysis') {
            steps {
                // Exécuter l'analyse SCA avec OWASP Dependency-Check
                sh 'dependency-check.sh --project MonProjet --scan .'
            }
        }

        stage('SAST Analysis') {
            steps {
                // Exécuter l'analyse SAST avec SonarQube
                sh 'sonar-scanner -Dsonar.projectKey=MonProjet -Dsonar.sources=.'
            }
        }

        stage('Build') {
            steps {
                // Construire le projet (exemple avec Maven)
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                // Déployer l'application (remplacez par votre script de déploiement)
                sh 'deploy.sh'
            }
        }

        stage('DAST Analysis') {
            steps {
                // Exécuter l'analyse DAST avec OWASP ZAP
                sh 'zap.sh -quickurl http://mon-app-deploye'
            }
        }
    }

    post {
        always {
            // Action à exécuter après chaque build, par exemple : notifier ou archiver les résultats
            echo 'Pipeline terminé.'
        }
    }
}
