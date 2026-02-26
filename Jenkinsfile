pipeline{
    
        agent any
    
    stages{
        stage("Build the images"){
            steps{
                echo "========Creating the images========"
                sh "docker compose build --no-cache"
            }
            post{
                success{
                    echo "========Build the images executed successfully========"
                    sh "docker images | grep log-analysis-pipeline"
                }
                failure{
                    echo "========Build the images execution failed========"
                }
            }
        }
    }
    
}