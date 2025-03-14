pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Compiling the C++ source code...'
                    sh 'g++ -o my_program my_program.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    sh './my_program'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the application...'
                    sh 'exit 1'
                }
            }
        }
    }

    post {
        failure {
            echo 'Pipeline Failed'
        }
        always {
            echo 'Cleaning up workspace...'
            sh 'rm -f my_program'
        }
    }
}
