pipeline {
    agent { docker { image 'python:3.8-slim-buster' } }

    stages {
        stage('build') {
            steps {
                sh 'pip3 install -r requirements.txt'
                sh 'python3 manage.py runserver'
            }
        }

        stage('test') {
            steps {
                sh 'python3 manage.py test'
            }
        }
    }

    post {
        success {
            echo 'Success: The pipeline was executed successfully'
        }
        failure {
            echo 'Failure: The pipeline has an error'
        }
    }
}