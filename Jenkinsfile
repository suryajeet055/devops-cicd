pipeline {
    agent any

    stages {

        stage('Checkout') {
    steps {
        git branch: 'main',
            url: 'https://github.com/suryajeet055/devops-cicd.git'
    }
}

        stage('Build') {
            steps {
                echo 'Building Application'
            }
        }

        stage('Test') {
            steps {
                sh 'test -f index.html'
                echo 'Application Test Successful'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t my-devops-app .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker rm -f my-devops-container || true'
                sh 'docker run -d --name my-devops-container -p 8081:80 my-devops-app'
            }
        }
    }
}
