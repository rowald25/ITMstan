pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/rowald25/ITMstan.git'
            }
        }
        stage('Build Frontend') {
            steps {
                script {
                    echo 'Building frontend application...'
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }
        stage('Security Test') {
            steps {
                script {
                    echo 'Running security tests...'
                    // Voeg hier je OWASP Dependency Check stappen toe
                    sh 'dependency-check.sh --project "MyProject" --scan . --format "ALL"'
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying project...'
            }
        }
    }
    post {
        always {
            dependencyCheckPublisher pattern: '**/dependency-check-report.xml'
        }
    }
}
