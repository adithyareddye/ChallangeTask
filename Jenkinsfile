pipeline {
    agent any
    environment {
        PLAYWRIGHT_BROWSERS_PATH = "
    C:\\Users\\dasar\\AppData\\Local\\ms-playwright"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/adithyareddye/ChallangeTask.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                script {
                    // Install npm dependencies
                    sh 'npm install'
                    // Install Playwright browsers (make sure browsers are installed)
                    sh 'npx playwright install'
                }
            }
        }
        stage('Run Playwright Tests') {
            steps {
                script {
                    // Run Playwright tests in headless mode by default (no need for --headless flag)
                    sh 'npx playwright test tests/e2e.test.ts --project=chromium'
                }
            }
        }
    }
}
