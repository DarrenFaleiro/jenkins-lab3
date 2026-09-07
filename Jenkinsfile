pipeline {
    agent {
        label 'Worker'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Build'
                sh 'pwd'
                sh 'ls'
                sh 'touch build.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Test'
                sh 'ls'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy'
                sh 'touch deploy.txt'
                sh 'mv deploy.txt build.txt'
                sh 'ls'
            }
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
