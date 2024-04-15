pipeline {
    agent any
    environment {
        NODEJS_HOME = "${tool 'NodeJS'}"
        PATH = "${env.NODEJS_HOME}/bin:${env.PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Aditya-567/TODO-NODEAPP-CI-CD.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'  // Your package.json must have a 'build' script
            }
        }
        stage('Deploy') {
            steps {
                // Add deployment commands here
                // Example: sh 'scp -r ./build yourserver:path/to/deploy'
                echo 'Deploy step goes here'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
    }
}
