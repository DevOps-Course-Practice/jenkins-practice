pipeline {
    agent any
    stages {
        stage('Build and Packaging') {
            steps {
                echo 'github webhook added'
                echo 'Hello Jenkins!'
                echo 'Building...'
                echo '---------------'
            }
        }

        stage('Testing'){
            steps{
                echo 'starting test...'
                echo '-----------------'
                echo 'finished test'
            }
        }

        stage('Code Scanning'){
            steps{
                echo 'scanning starting...'
                echo 'scanning completed'
            }
        }

        stage('Push Artifacts'){
            steps{
                echo 'push the build artifacts'
                echo 'completed'
            }
        }

    }
}
