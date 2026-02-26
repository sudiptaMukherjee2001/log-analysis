pipeline{
    
        agent any
    
    stages{
        stage("Build the images"){
            steps{
                echo "========Creating the images========"
                sh "docker compose up --build"
            }
            post{
                success{
                    echo "========Build the images executed successfully========"
                }
                failure{
                    echo "========Build the images execution failed========"
                }
            }
        }
    }
    
}