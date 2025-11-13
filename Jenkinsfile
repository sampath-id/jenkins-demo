pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    credentialsId: 'github-cred',
                    url: 'https://github.com/sampath-id/jenkins-demo.git'
            }
        }
        stage('Build') {
            steps {
                sh 'chmod +x app.sh'
                sh './app.sh'
            }
        }
    }
    post {
        success {
            echo "✅ Jenkins build successful!"
        }
        failure {
            echo "❌ Jenkins build failed!"
        }
    }
}
