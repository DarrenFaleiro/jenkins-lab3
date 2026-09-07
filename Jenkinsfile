// pipeline {
//     agent {
//         label 'Worker'
//     }

//     stages {

//         stage('Build') {
//             steps {
//                 echo 'Build'
//                 sh 'pwd'
//                 sh 'ls'
//                 sh 'touch build.txt'
//             }
//         }

//         stage('Test') {
//             steps {
//                 echo 'Test'
//                 sh 'ls'
//             }
//         }

//         stage('Deploy') {
//             steps {
//                 echo 'Deploy'
//                 sh 'touch deploy.txt'
//                 sh 'mv deploy.txt build.txt'
//                 sh 'ls'
//             }
//         }
//     }

//     post {
//         success {
//             echo 'Pipeline completed successfully!'
//         }

//         failure {
//             echo 'Pipeline failed!'
//         }

//         always {
//             echo 'Pipeline has finished.'
//         }
//     }
// }

// ============================================================


pipeline {
    agent {
        label 'worker'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Getting the project'
                sh 'git clone https://gitlab.com/Reece-Elder/dockerfileexercise.git'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image'
                sh 'cd dockerfileexercise && docker build -t myapp .'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application'
                sh 'docker stop myapp || true'
                sh 'docker rm myapp || true'
                sh 'docker run -d --name myapp -p 8080:80 myapp'
            }
        }
    }
}
