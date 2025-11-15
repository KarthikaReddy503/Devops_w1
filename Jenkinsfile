pipeline {
    agent any

    environment {
        PYTHON = "python"   // change to "python3" if needed
    }

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning GitHub repository...'
                git 'https://github.com/KarthikaReddy503/Devops_w1.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing Python dependencies...'
                bat "${env.PYTHON} -m pip install --upgrade pip"
                bat "${env.PYTHON} -m pip install -r requirements.txt"
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage - nothing to compile for Python'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running Flask app briefly for demo...'
                bat "${env.PYTHON} app.py"
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage - you can add actual tests if you have any'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed!'
        }
        success {
            echo 'Pipeline succeeded.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
