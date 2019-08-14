pipeline {
  agent any 
  stages {
    stage('Build') { 
      steps {
       echo 'In build stage'
            sh '''dotnet restore WebAPIs.sln --source https://api.nuget.org/v3/index.json
        
              dotnet build WebAPIs.sln -p:CONFIGURATION=release -V:n '''
      }
    }

    stage('Test') { 
      steps {
    	echo 'In test stage'
          sh 'dotnet test WebApiTests/WebApiTests.csproj'
      }
    }
  }
}
