pipeline {
    agent any
    
    stages {
        stage('Restore Dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Run Test') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
