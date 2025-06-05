pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("my-python-app:${env.BUILD_NUMBER}", "python-jenkins-argocd-k8s/")
                }
            }
        }
        stage('Run Docker Image') {
            steps {
                script {
                    sh 'docker run --rm my-python-app:' + env.BUILD_NUMBER + ' python --version'
                }
            }
        }
    }
}
