pipeline {
    agent any

    environment {
        PYTHON = "python" // Use "python3" on Linux if needed
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/nainamedar/ExamDevops.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh "${env.PYTHON} -m pip install --upgrade pip"
                sh "${env.PYTHON} -m pip install -r requirements.txt"
            }
        }

        stage('Run Tests') {
            steps {
                sh "${env.PYTHON} -m unittest test_app.py"
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Python application...'
                script {
                    // Simulate deploy: print or archive
                    echo 'App deployed to /opt/python-app!'
                }
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace...'
        }
        success {
            echo 'Build and tests successful!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
