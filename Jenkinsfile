pipeline {
    agent any
    
    stages {
        stage('SCM Checkout') {
            steps {
                retry(3) {
                    git branch: 'main', url: 'https://github.com/HGSChandeepa/test-node'
                }
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t udanasanchitha/nodeapp:${BUILD_NUMBER} .'
            }
        }
        stage('Login to Docker Hub') {
            steps {
                withCredentials([string(credentialsId: 'sanchitha', variable: 'password')]) {
                    script {  
                        sh "docker login -u adomicarts -p '${samindocker}'"
                    }
                }
            }
        }
        stage('Push Image') {
            steps {
                sh "docker push udanasanchitha/nodeapp:${BUILD_NUMBER}"
            }
        }
    }
    post {
        always {
            sh 'docker logout'
        }
    }
}
