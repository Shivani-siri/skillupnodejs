pipeline {
    agent any

    environment {
        NODE_ENV = 'production'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-repo/skillupnodejs.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    sh 'npm test' // Make sure you have tests in package.json
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t skillupnodejs:latest .'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh 'docker run -d -p 3000:3000 skillupnodejs:latest'
                }
            }
        }
    }
}
