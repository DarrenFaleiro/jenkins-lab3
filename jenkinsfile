pipeline {
    agent {
        label 'Worker'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Starting Build stage...'
                pwd
                sh 'ls -la'
                sh 'touch build.txt'
                echo 'Build completed.'
            }
        }

        stage('Test') {
            steps {
                echo 'Starting Test stage...'
                sh 'ls -la'
                echo 'Running tests...'
                echo 'Tests passed.'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Starting Deploy stage...'
                sh 'touch deploy.txt'
                sh 'mv deploy.txt build.txt'
                sh 'ls -la'
                echo 'Deployment completed.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }

        always {
            echo 'Pipeline has finished.'
        }
    }
}
