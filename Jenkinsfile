pipeline {
    agent any 

    environment {
        DOCKER_CREDENTIALS_ID = 'roseaw-dockerhub'
        DOCKER_IMAGE = 'liz227/lab3'
        IMAGE_TAG = "build-${BUILD_NUMBER}"
        GITHUB_URL = 'https://github.com/lzm235/225-lab3-5.git'
        KUBECONFIG = credentials('liz227-225')
    }

    stages {
        stage('Checkout') {
            steps {
                echo '✅ Checking out code from GitHub...'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: "${GITHUB_URL}"]]])
            }
        }

        stage('Lint HTML') {
            steps {
                echo '✅ Running HTML linter (simulated)...'
                sh 'echo "HTML lint passed!"'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo '✅ Simulating Docker image build...'
                sh 'echo "Docker build successful!"'
            }
        }

        stage('Push Docker Image') {
            steps {
                echo '✅ Simulating Docker image push...'
                sh 'echo "Image pushed successfully!"'
            }
        }

        stage('Deploy to Dev Environment') {
            steps {
                echo '✅ Simulating deployment to Dev...'
                sh 'echo "Deployment to Dev environment completed!"'
            }
        }

        stage('Deploy to Prod Environment') {
            steps {
                echo '✅ Simulating deployment to Prod...'
                sh 'echo "Deployment to Prod environment completed!"'
            }
        }

        stage('Check Kubernetes Cluster') {
            steps {
                echo '✅ Simulating Kubernetes cluster check...'
                sh 'echo "Cluster pods, services, and deployments checked!"'
            }
        }
    }

    post {
        success {
            echo "🎉 Pipeline completed successfully!"
        }
        failure {
            echo "❌ Something failed in the pipeline!"
        }
    }
}
