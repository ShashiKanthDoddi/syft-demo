pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                git branch: 'main', url: 'https://github.com/ShashiKanthDoddi/syft-demo'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Node.js and NPM
                sh 'curl -sL https://deb.nodesource.com/setup_16.x | bash -'
                sh 'apt-get install -y nodejs'

                // Install project dependencies
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                // Build project
                sh 'npm run build'
            }
        }

        stage('Run') {
            steps {
                // Start the server
                sh 'npm start'
            }
        }
    }
    
    post {
        always {
            // Clean up workspace
            deleteDir()
        }
    }
}
