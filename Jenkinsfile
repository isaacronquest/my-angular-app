pipeline {
    agent any
    environment {
        CHROME_BIN = '/usr/bin/google-chrome' // Adjust this path as necessary
    }
    tools {nodejs "NODEJS"}
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') { // Adding a Test stage
            steps {
                sh 'npm test' // Assuming you have tests configured in your package.json
            }
        }
        stage('Deliver') {
            steps {
                sh 'chmod -R +rwx ./jenkins/scripts/deliver.sh'
                sh 'chmod -R +rwx ./jenkins/scripts/kill.sh'
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
