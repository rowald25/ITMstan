pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git brnch: 'main', url 'https://github.com/rowald25/ITMstan.git'
            }
        }
        stage('build') {
            steps {
                echo 'building project...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying project...'
            }
        }
    }
}
