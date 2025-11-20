pipeline {
    agent any
    triggers {
        githubPush()  // Webhook trigger
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/user/mavenpipeline.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'  // uses pom.xml
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
    post {
        success {
            echo 'Build successful via GitHub Webhook'
        }
        failure {
            echo 'Build failed'
        }
    }
}
