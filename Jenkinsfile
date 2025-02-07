pipeline {
    agent any

    environment {
        GIT_CREDENTIALS_ID = 'jenkins-two'  // Replace with the actual credentials ID in Jenkins
        GIT_REPO = 'https://github.com/EslamMOsman/my-weather-app.git'
        GIT_BRANCH = 'main'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout([
                        $class: 'GitSCM',
                        branches: [[name: "*/${env.GIT_BRANCH}"]],
                        userRemoteConfigs: [[
                            url: env.GIT_REPO,
                            credentialsId: env.GIT_CREDENTIALS_ID
                        ]]
                    ])
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'echo "Building the application..."'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'echo "Running tests..."'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh 'echo "Deploying the application..."'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
