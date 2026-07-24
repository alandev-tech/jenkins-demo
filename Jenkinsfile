pipeline {
    agent any
    environment {
        IMAGE_NAME = "jenkins-demo"
    }
    parameters {
    string(
        name: 'IMAGE_TAG',
        defaultValue: 'v1',
        description: 'Enter Docker Image Tag'
    )
}

    stages {

        stage('Checkout Success') {
            steps {
                echo 'Code downloaded successfully from GitHub.'
            }
        }

        stage('Build Docker Image') {
            steps {
               sh "docker build -t ${IMAGE_NAME}:${params.IMAGE_TAG} ."
            }
        }

        stage('List Docker Images') {
            steps {
                sh 'docker images'
            }
        }
        
        stage('Run Docker Container') {
        steps {
           sh "docker run --rm ${IMAGE_NAME}:${params.IMAGE_TAG}"
         }
     }
}

    post {
        success {
            echo 'Docker Image Build Completed Successfully!'
        }
    }
}
