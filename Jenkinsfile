pipeline {
    agent any
    
    environment {
        
        DOCKERHUB_CREDS = credentials('dockerhub-creds')
        IMAGE_NAME = ravikumarr10839/react-trend-app"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:latest .'
            }
        }
        
        stage('Push to DockerHub') {
            steps {
                sh 'echo $DOCKERHUB_CREDS_PSW | docker login -u $DOCKERHUB_CREDS_USR --password-stdin'
                sh 'docker push $IMAGE_NAME:latest'
            }
        }
        
        stage('Deploy to EKS') {
            steps {
                
                sh 'kubectl apply -f k8s-deploy.yaml'
            }
        }
    }
    
    post {
        success {
            mail to: 'ravimali7700@gmail.com',
                 subject: 'SUCCESS: React Trend App Pipeline',
                 body: 'Great job! The pipeline completed successfully and the application is deployed to the EKS cluster.'
        }
        failure {
            mail to: 'ravimali7700@gmail.com',
                 subject: 'FAILURE: React Trend App Pipeline',
                 body: 'The pipeline failed. Please check the Jenkins console output to debug.'
        }
    }
}
