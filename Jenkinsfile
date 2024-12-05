pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'yuvrajdocker', toolName: 'docker') {
                        sh "docker build -t yuvrajdocker001/checkoutservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'yuvrajdocker', toolName: 'docker') {
                        sh "docker push  yuvrajdocker001/checkoutservice:latest "
                    }
                }
            }
        }
    }
}
