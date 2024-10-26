pipeline {
    agent any 

    stages {
        stage('Checkout Repo') {
            steps {
                git 'https://github.com/ihristoff/SEDO-Regular-Exam-2024-10.git'
            }
        }

        stage('Restore') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --no restore'
            }
        }

        stage('Run Unit and Integration Tests') {
            steps {
                bat 'dotnet test HouseRentingSystem.UnitTests/HouseRentingSystem.UnitTests.csproj --no-build --verbosity normal'
                bat 'dotnet test HouseRentingSystem.Tests/HouseRentingSystem.Tests.csproj --no-build --verbosity normal'
            }
        }
       
    }

    
}
