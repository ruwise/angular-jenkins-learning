pipeline {
    agent any
    environment {
        NODEJS_HOME = tool 'NODE20' // Use configured NodeJS tool name
        PATH = "${NODEJS_HOME}/bin:${env.PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/ruwise/angular-jenkins-learning.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                bat 'npm run test -- --watch=false --browsers=ChromeHeadless'
            }
        }
        stage('Build Angular App') {
            steps {
                bat 'npm run build -- --configuration=production'
            }
        }
        
    }
}
