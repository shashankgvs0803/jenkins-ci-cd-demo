pipeline {
    agent any   // run on any available agent

    triggers {
        pollSCM('H/2 * * * *')   // checks repo every 2 mins for new commits
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                git branch: 'main', url: 'https://github.com/shashankgvs0803/jenkins-ci-cd-demo.git'

            }
        }

        stage('Build') {
            steps {
                echo 'Running Python application...'
                bat 'main.py'      // For Windows
                // sh 'python3 main.py'   // For Linux/Mac
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                bat 'echo Deployment complete!'
            }
        }
    }

    post {
        success {
            echo 'Build & Deployment Successful!'
        }
        failure {
            echo ' Build Failed!'
        }
    }
}
