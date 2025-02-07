pipeline {
    agent any

    environment {
        GITHUB_TOKEN = credentials('jenkins')  
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    sh 'git clone https://$GITHUB_USER:$GITHUB_TOKEN@github.com/EslamMOsman/my-weather-app.git'
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
    }
}

