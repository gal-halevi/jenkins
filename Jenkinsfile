// Multibranch - one Jenkinsfile, different behaviour per branch. Setup and what to show: README.md

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building branch ${env.BRANCH_NAME}"
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
        stage('Deploy staging') {
            when { branch 'develop' }
            steps {
                echo 'Deploying to staging'
            }
        }
        stage('Deploy production') {
            when { branch 'main' }
            steps {
                echo 'Deploying to production'
            }
        }
    }
}
