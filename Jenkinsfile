pipeline {
    agent any

    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['DEV', 'TEST', 'PROD'],
            description: 'Select deployment environment'
        )
    }

    environment {
        APP_NAME = 'MyApplication'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Build is running'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying to ${params.ENVIRONMENT}"
            }
        }

        stage('Deploy to PROD') {
            when {
                expression {
                    params.ENVIRONMENT == 'PROD'
                }
            }

            steps {
                echo 'Deploying to Production'
            }
        }
    }
}
