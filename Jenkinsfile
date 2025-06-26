pipeline{
    agent any

    stages{
        stage("Build"){
            when {
                anyOf {
                    branch 'main'
                    branch pattern: "feature/.*", comparator: "REGEXP"   
                }
            }
            steps{
                echo "========Building the project========"
                bat "dotnet build"
            }
  
        }
    }

    stage("Test"){
            when {
                anyOf {
                    branch 'main'
                    branch pattern: "feature/.*", comparator: "REGEXP"   
                }
            }
        steps{
            echo "========Running tests========"
            bat "dotnet test"
        }
    }
}