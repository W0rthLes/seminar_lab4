pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Клонируем ваш репозиторий
                git branch: 'master', url: 'https://github.com/W0rthLes/seminar_lab4.git'
            }
        }

        stage('Install dependencies') {
            steps {
                // Установка зависимостей через pip
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                // Запуск тестов
                sh 'python -m unittest discover'
            }
        }
    }

    post {
        always {
            // Всегда архивируем результаты сборки
            archiveArtifacts artifacts: '**/tests/*.py', allowEmptyArchive: true
        }
    }
}
