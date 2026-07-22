pipeline {
    agent any

    stages {

        stage('Checkout Success') {
            steps {
                echo 'Code downloaded successfully from GitHub.'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-demo:v1 .'
            }
        }

        stage('List Docker Images') {
            steps {
                sh 'docker images'
            }
        }
    }

    post {
        success {
            echo 'Docker Image Build Completed Successfully!'
        }
    }
}
    stage('Run Docker Container') {
        steps {
            sh 'docker run --rm jenkins-demo:v1'
    }
}
