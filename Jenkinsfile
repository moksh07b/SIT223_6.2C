pipeline {
    agent any
    
    environment {
        DIRECTORY_PATH = 'https://github.com/moksh07b/SIT223_Task_5.1P'
        TESTING_ENVIRONMENT = 'Staging'
        PRODUCTION_ENVIRONMENT = 'Moksh'
    }
    
    stages {    // Multiple Stages
        stage('Build') {    //Single Stage
            steps {         //Add Steps to the stage    
                echo "Fetch the source code from the directory path: ${DIRECTORY_PATH}"
                echo "Compile the code and generateany necessary artifacts"
            }
        }
        
        stage('Test') {
            steps {
                echo "Unit tests"
                echo "Integration tests"
            }
        }
        
        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deploying to ${TESTING_ENVIRONMENT} environment"
            }
        }
        
        stage('Approval') {
            steps {
                echo "Waiting for manual approval to proceed to production deployment"
                sleep 10
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deploying to production environment: ${PRODUCTION_ENVIRONMENT}"
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
