pipeline {
    agent any

    stages {

        stage('Hello') {
            steps {
                echo 'webhook test successfully'
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
        }

        always {
            echo 'Pipeline execution finished.'
        }
    }
}
