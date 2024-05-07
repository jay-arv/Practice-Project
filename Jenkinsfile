pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from Git
                git 'https://github.com/jay-arv/Practice-Project.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install Node.js and npm
                // Adjust the version numbers as needed
                sh 'curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -'
                sh 'sudo apt-get install -y nodejs'
                
                // Install project dependencies
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                // Build the React project
                sh 'npm run build'
            }
        }
        
        stage('Deploy') {
            steps {
                // Copy the built artifacts to the deployment directory
                sh 'cp -R build/* /path/to/deployment/directory'
                
                // Optionally, deploy to a web server or hosting platform
                // Add deployment steps here (e.g., using rsync, SCP, or FTP)
            }
        }
    }
    
    post {
        always {
            // Clean up workspace
            cleanWs()
        }
    }
}
