pipeline{
    
        label any
    
    stages{
        stage("Build the images"){
            steps{
                echo "========Creating the images========"
                sh "docker build -t log-analyzer-though-pipeline:${BUILD_NUMBER} ."
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