pipeline {
    agent any

    tools {
        nodejs 'node16'
    }

    stages {
        stage('Git checkout') {
            steps {
                git 'https://github.com/betawins/Trading-UI.git'
            }
        }

        stage('Install npm prerequisites'){
            steps{
                sh 'npm audit fix'
                sh 'npm install'
                sh 'npm run build'
                sh 'cd build && pm2 --name Trading-UI start npm -- start'
            }
        }
    }
}

