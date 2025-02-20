pipeline {
    agent {
        docker {
            image 'mcr.microsoft.com/dotnet/sdk:6.0'
            // Use the appropriate user if needed:
            args '-u root:root'
        }
    }
    stages {
        stage('Restore Dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run Test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
