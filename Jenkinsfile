pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/Joeseb/PES121CS249_Jenkins.git']]
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
