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
            post {
                always {
                    junit 'junit.xml'  // Jest test results (via jest-junit)
                    publishHTML(target: [
                        allowMissing: false,
                        alwaysLinkToLastBuild: true,
                        keepAll: true,
                        reportDir: 'coverage',
                        reportFiles: 'lcov-report/index.html',
                        reportName: 'Jest Coverage Report'
                    ])
                }
            }
        }
    }
}