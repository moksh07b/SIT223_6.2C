pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Installing dependencies using npm"
                echo 'npm install'
                echo "Building the application using npm"
                echo 'npm run build'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests using npm"
                echo 'npm run test:unit'
                echo "Running integration tests using npm"
                echo 'npm run test:integration'
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Performing code analysis using eslint"
                echo 'npm run lint'
            }
        }

        stage('Security Scan') {
            steps {
                echo "Performing security scan using npm audit"
                echo 'npm audit'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying to Staging Server using npm"
                echo 'npm run deploy:staging'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on staging environment"
                echo 'npm run test:staging'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying to Production Server using npm"
                echo 'npm run deploy:production'
            }
        }
    }

    post {
        success {
            emailext subject: 'Jenkins Pipeline Success', 
             body: 'The pipeline has completed successfully.', 
             to: 'mokshbansal07@gmail.com'
        }
        
        failure {
            echo 'Pipeline failed!'
            emailext subject: 'Jenkins Pipeline Failure', 
                     body: 'The pipeline has failed. Please check the logs.', 
                     to: 'mokshbansal07@gmail.com'
        }
    }
}
