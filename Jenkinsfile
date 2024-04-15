pipeline {
    agent any
    
    // Define the tools to use. Jenkins will use the NodeJS installation defined in the Global Tool Configuration.
    tools {
        nodejs 'NodeJS'
    }
    
    stages {
        stage('Checkout') {
            steps {
                // This step is handled automatically by Jenkins when the Pipeline job starts.
                echo 'Checking out the code...'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // This will run 'npm install' in the root directory where your project is checked out.
                sh 'npm install'
            }
        }
        
        stage('Run Tests') {
            steps {
                // This will run 'npm test'. Make sure you have your test scripts defined in your package.json.
                sh 'npm test'
            }
        }
        
        stage('Build') {
            steps {
                // This will run 'npm run build'. Ensure you have a 'build' script in your package.json.
                sh 'npm run build'
            }
        }
        
        stage('Deploy') {
            steps {
                // Here you add your deployment commands.
                // This is just a placeholder; you must replace it with actual deployment commands.
                echo 'Deployment step will be executed here.'
            }
        }
    }
    
    post {
        always {
            // This block runs after the stages no matter the result.
            echo 'The Pipeline has finished executing.'
        }
        success {
            // This block runs only if the Pipeline succeeds.
            echo 'Build was successful. Deployment can proceed.'
        }
        failure {
            // This block runs only if the Pipeline fails.
            echo 'Build failed. Check the logs for errors.'
        }
    }
}
