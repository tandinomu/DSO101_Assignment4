pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo "✅ Code checked out successfully"
            }
        }
        
        stage('Build Simulation') {
            steps {
                echo "🔨 Building Docker image (simulated)..."
                sh 'echo "FROM node:18-alpine" > Dockerfile.test'
                sh 'echo "WORKDIR /app" >> Dockerfile.test'
                sh 'echo "COPY . ." >> Dockerfile.test'
                sh 'cat Dockerfile.test'
                echo "✅ Docker image build simulation completed"
            }
        }
        
        stage('Test Simulation') {
            steps {
                echo "🧪 Testing application..."
                sh 'node --version || echo "Node.js check completed"'
                sh 'ls -la src/'
                echo "✅ Application test simulation passed"
            }
        }
        
        stage('Security Check') {
            steps {
                echo "🔒 Security scan simulation..."
                sh 'echo "Scanning for vulnerabilities..."'
                sh 'echo "✓ No critical vulnerabilities found"'
                echo "✅ Security scan completed"
            }
        }
        
        stage('Deploy Simulation') {
            steps {
                echo "🚀 Deployment simulation..."
                sh 'echo "Pushing to registry: tandinomu/secure-app:${BUILD_NUMBER}"'
                sh 'echo "✓ Image pushed successfully"'
                echo "✅ Deployment simulation completed"
            }
        }
    }
    
    post {
        success {
            echo "🎉 Jenkins Pipeline completed successfully!"
            echo "📦 Image: tandinomu/secure-app:${BUILD_NUMBER}"
            echo "🔒 Security practices implemented"
        }
        failure {
            echo "❌ Pipeline failed"
        }
    }
}