pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/W0rthLes/seminar_lab4.git'
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'python -m unittest discover'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/tests/*.py', allowEmptyArchive: true
        }
    }
}
