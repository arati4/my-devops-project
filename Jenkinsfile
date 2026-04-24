pipeline {
    agent any

    stages {

        stage('Pull Code') {
            steps {
                echo "Code pulled successfully"
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building project...'
            }
        }

        stage('Test') {
            steps {
                sh 'echo Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo Deploying app...'
            }
        }
    }
}
