pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://thub.com/PES2UG22CS190/CC_Lab8/']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES2UG22CS190-1'
                sh 'g++ test.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
           echo 'error Pipeline failed'
        }
    }
}
