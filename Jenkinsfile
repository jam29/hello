pipeline {
    agent any

    tools {
        nodejs 'nodejs'  // Must match Jenkins Node.js installation name
    }

    stages {

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
          
        }
    }
}