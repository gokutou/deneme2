pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', 
                    credentialsId: 'github-access', 
                    url: 'https://github.com/gokutou/deneme2.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Application') {
            steps {
                sh 'npm start'
            }
        }
    }
}
