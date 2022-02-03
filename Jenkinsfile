pipeline {
  agent { label 'nodejs' }
    stages {
      stage('Checkout') {
        steps {
          git branch: 'main', url: 'https://github.com/djadk84/devops-ci.git'
          }
        }
      stage('Install') {
        steps {
          sh 'cd codebase/rdicidr-0.1.0 && npm install'
          sh 'cd codebase/rdicidr-0.1.0 && npm install prettier'
          }
        }
      stage('Linter & Formatter') {
        steps {
          sh 'cd codebase/rdicidr-0.1.0 && npm run lint'
          sh 'cd codebase/rdicidr-0.1.0 && npm  run prettier'
          }
        }
      stage('Nodejs testing') {
        steps {
          sh 'cd codebase/rdicidr-0.1.0 && CI=true npm run test'
          }
        }
      stage('Build') {
        steps {
          sh 'cd codebase/rdicidr-0.1.0 && npm run build'
          }
        }
      }
  }
