pipeline {
    agent any
    environment {
        PLAYWRIGHT_BROWSERS_PATH = 'C:\\Users\\dasar\\AppData\\Local\\ms-playwright' // Custom path
    }
    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    // Install Playwright dependencies
                    bat 'npm install'
                }
            }
        }
        stage('Run Playwright Tests') {
            steps {
                script {
                    // Ensure browsers are installed in the custom path
                    bat 'npx playwright install'
                    // Run Playwright tests
                    bat 'npx playwright test tests/e2e.test.ts'
                }
            }
        }
    }
}
