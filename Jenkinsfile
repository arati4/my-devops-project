pipeline {
    agent any

    environment {
        AWS_REGION = "ap-south-1"
        ECR_REPO = "885820157422.dkr.ecr.ap-south-1.amazonaws.com/my-devops-app"
    }

    stages {

        stage('Pull Code') {
            steps {
                echo "Code pulled"
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Login to ECR') {
            steps {
                sh '''
                aws ecr get-login-password --region $AWS_REGION \
                | docker login --username AWS --password-stdin $ECR_REPO
                '''
            }
        }

        stage('Push Image') {
            steps {
                sh '''
                docker tag my-app:latest $ECR_REPO:latest
                docker push $ECR_REPO:latest
                '''
            }
        }
    }
}
