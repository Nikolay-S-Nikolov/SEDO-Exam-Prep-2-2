pipeline {
    agent any

    stages {
        stage('Build') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'echo Building the project...'
                bat 'dotnet build'
            }
        }

        stage('Test') {
            when {
                branch 'feature-ci-pipeline'
            }
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