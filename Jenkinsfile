pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'make'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'make check'
                junit '**/test-*.xml'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'make publish'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment succeeded!'
        }
        failure {
            echo 'Build or deployment failed.'
        }
    }
}
