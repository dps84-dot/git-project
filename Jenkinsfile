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

        stage('Linux Commands') {
            steps {
                sh '''
                    echo "Current directory:"
                    pwd

                    echo "Files:"
                    ls -la
                '''
            }
        }

        stage('Build') {
            steps {
                echo 'Build is running'
                script {
    try {
        sh 'some-command'
    } catch (err) {
        echo 'Error handled successfully'
        retry(3) {
    sh 'echo "Trying command..."'
}
    }
}
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
