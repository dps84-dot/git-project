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
                echo "Building ${APP_NAME}"
            }
        }
    }
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
    }
}
