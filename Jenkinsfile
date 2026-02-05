pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'javac Hello.java'
            }
        }

        stage('Test') {
            steps {
                sh 'java Hello'
            }
        }
    }

    post {
        success {
            echo 'CI PIPELINE SUCCESS'
        }
        failure {
            echo 'CI PIPELINE FAILED'
        }
        always {
            archiveArtifacts artifacts: '*.class'
        }
    }
}
