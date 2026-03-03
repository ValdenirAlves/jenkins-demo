pipeline {
    agent {
        docker {
            image 'node:20'
        }
    }

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t jenkins-demo .'
            }
        }

        stage('Simulated Deploy') {
            steps {
                echo 'Simulating deploy...'
                sh 'docker run -d -p 4000:3000 jenkins-demo'
            }
        }
    }
}