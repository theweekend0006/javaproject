pipeline {
    agent any
    triggers {
        githubPush()  // Webhook trigger
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Code already cloned by Jenkinsfile SCM'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build successful via webhook'
        }
        failure {
            echo 'Build failed'
        }
    }
}
