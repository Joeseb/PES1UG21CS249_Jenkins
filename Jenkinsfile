pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: '']]
                ])
            }
        }

        stage('Build') {
            steps {
                sh 'g++ -o hello ./main/hello.cpp'
            }
        }

        stage('Test') {
            steps {
                sh './hello'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying..."
            }
        }
    }

    post {
        failure {
            echo "Pipeline Failed"
        }
    }
}
