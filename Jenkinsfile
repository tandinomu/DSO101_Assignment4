pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo "✅ Code checked out successfully"
            }
        }
        
        stage('Build') {
            steps {
                echo "🔨 Building Docker image..."
                sh 'docker build -t tandinomu/secure-app:${BUILD_NUMBER} .'
                echo "✅ Docker image built successfully"
            }
        }
        
        stage('Test') {
            steps {
                echo "🧪 Testing Docker image..."
                sh 'docker run --rm tandinomu/secure-app:${BUILD_NUMBER} node --version'
                echo "✅ Docker image test passed"
            }
        }
        
        stage('Success') {
            steps {
                echo "🎉 Pipeline completed successfully!"
                echo "📦 Image: tandinomu/secure-app:${BUILD_NUMBER}"
            }
        }
    }
    
    post {
        success {
            echo "✅ All stages completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed at some stage"
        }
    }
}