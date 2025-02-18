pipeline {
    agent any

    environment {
        PROJECT_NAME = 'MyApp'
        BUILD_DIR = 'build'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/example/repo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'make build' // Change this based on your build process
            }
        }

        stage('Test') {
            steps {
                sh 'make test' // Run your test commands
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                sh 'deploy.sh' // Deployment script
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
