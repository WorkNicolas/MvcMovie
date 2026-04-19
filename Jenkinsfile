pipeline {
    agent any
    
    environment {
        // Define project-specific variables
        SOLUTION_FILE = 'MvcMovie.sln'
        PROJECT_FILE = 'MvcMovie/MvcMovie.csproj'
    }
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code from GitHub...'
                checkout scm
                echo 'Checkout complete!'
            }
        }
        
        stage('Restore Dependencies') {
            steps {
                echo 'Restoring NuGet packages...'
                bat 'dotnet restore "%PROJECT_FILE%"'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'dotnet build "%PROJECT_FILE%" --configuration Release --no-restore'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                echo 'Test stage - will add actual tests later'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
        always {
            echo 'Cleaning up workspace...'
            cleanWs()
        }
    }
}
