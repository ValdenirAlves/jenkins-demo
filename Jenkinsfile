pipeline {
    agent any  // usa o container Jenkins

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build & Test') {
            agent { docker { image 'node:20' } }  // container Node só para npm
            steps {
                sh 'npm install'
                sh 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-demo .'  // RODA NO CONTAINER JENKINS, TEM CLI!
            }
        }

        stage('Simulated Deploy') {
            steps {
                echo 'Deploy skipped'
            }
        }
    }
}