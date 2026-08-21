Pipeline script:
pipeline {
    agent any

    tools {
        maven 'maven'
        jdk 'java'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master',
                    url: 'git@github.com:24wh1a0550/jenkins.git',
                    credentialsId: 'admin'
            }
        }

        stage('Build & Test') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Deploy (Optional)') {
            steps {
                echo " Deployment stage (add steps if needed)"
            }
        }
    }

    post {
        success {
            echo "✅ Pipeline completed successfully!"
        }
        failure {
            echo "❌ Build failed. Check logs above."
        }
    }
}
