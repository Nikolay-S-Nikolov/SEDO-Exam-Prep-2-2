pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'echo Building the project...'
                bat 'dotnet build'
            }
        }

        stage('Test') {
            steps {
                bat 'echo Running tests...'
                bat 'dotnet test' 
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Build and tests succeeded!'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}