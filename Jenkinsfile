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
                        retry(3) {
                            sh 'some-command'
                        }
                    } catch (err) {
                        echo 'Error handled successfully'
                    }

                    sh '''
                        echo "Build Report" > report.txt
                    '''

                    archiveArtifacts artifacts: 'report.txt',
                                      fingerprint: true
                }
            }
        }

        stage('Testing') {
            parallel {

                stage('Unit Test') {
                    steps {
                        echo 'Unit Test running'
                    }
                }

                stage('Security Test') {
                    steps {
                        echo 'Security Test running'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying to ${params.ENVIRONMENT}"
            }
        }

        stage('Approval') {
            steps {
                input message: 'Deploy to Production?',
                      ok: 'Proceed'
            }
        }

        stage('Deploy to PROD') {
            steps {
                echo 'Deploying to Production'
            }
        }
    }
}
