pipeline {
  agent any
  stages {
    stage('Checkout code') {
      steps {
        git branch: 'main', url:'https://github.com/sureshthumar/PlaywrightDemo.git'
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
    stage('Run Playwright tests') {
      steps {
        sh 'npx playwright test --reporter=html'
      }
    }
    stage('Upload HTML report') {
      steps {
        publishHTML target: [
          allowMissing: false,
          alwaysLinkToLastBuild: true,
          keepAll: true,
          reportDir: 'playwright-report',
          reportFiles: 'index.html',
          reportName: 'Playwright Test Report'
        ]
      }
    }
}
    }
  }
}

