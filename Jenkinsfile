pipeline {
    agent any

    tools {
        nodejs 'NODEJS'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'ng build --prod'
            }
        }

        stage('Test') {
            steps {
                sh 'ng test'
            }
        }

        stage('E2E Tests') {
            steps {
                sh 'ng e2e'
            }
        }
    }
}