pipeline {
    agent any
    triggers { githubPush() }

    stages {
        stage('Checkout') {
            steps {
                echo 'Code already cloned by Jenkinsfile SCM'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success { echo 'Build successful via webhook' }
        failure { echo 'Build failed' }
    }
}
