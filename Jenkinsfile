pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/rowald25/ITMstan.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building project...'
                // Voeg hier je daadwerkelijke build stappen toe, bijvoorbeeld:
                // bat 'npm install'
                // bat 'npm run build'
            }
        }
        stage('OWASP Dependency Check') {
            steps {
                bat 'dependency-check.bat --project "MyProject" --scan . --format "ALL"'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying project...'
                // Voeg hier je daadwerkelijke deploy stappen toe
            }
        }
    }
    post {
        always {
            dependencyCheckPublisher pattern: '**/dependency-check-report.xml'
        }
    }
}
