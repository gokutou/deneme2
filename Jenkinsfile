pipeline{
    agent any

    tools {
         nodejs '1'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', 
                    credentialsId: 'github-access', 
                    url: 'https://github.com/gokutou/deneme2.git'
            }
        }
        stage('get_version') {
            steps {
                script {
                    def version = sh(script: "node -e \"console.log(require('./package.json').version)\"", returnStdout: true).trim()
                    echo "Project Version: ${version}"
                }
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
