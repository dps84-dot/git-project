pipeline {
    agent any

    stages {

        stage('Hello') {
            steps {
                echo 'webhook auto build test'
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage is running'
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage is running'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage is running'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        } //webhook test

        always {
            echo 'Pipeline execution finished.'
        }
    }
}
