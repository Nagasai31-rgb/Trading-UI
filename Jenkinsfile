pipeline {
    agent any

    stages {

        stage('Git checkout') {
            steps {
                git 'https://github.com/betawins/Trading-UI.git'
            }
        }

        stage('Install npm prerequisites') {
            steps {
                sh 'npm install'
                sh 'npm run build'
                sh 'pm2 delete Trading-UI || true'
                sh 'pm2 start npm --name "Trading-UI" -- start'
            }
        }
    }
}

