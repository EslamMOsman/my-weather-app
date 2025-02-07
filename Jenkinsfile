pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', credentialsId: 'github-credentials', url: 'https://github.com/eslam3toss/my-weather-app.git'
            }
        }

        stage('Start Server') {
            steps {
                script {
                    sh 'nohup python3 -m http.server 9090 --directory . > server.log 2>&1 &' 
                }
            }
        }
    }
}

