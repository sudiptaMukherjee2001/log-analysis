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
                    echo "========Image build successfully========"
                    sh "docker images | grep log-analysis-pipeline"

                }
                failure{
                    echo "========Build the images execution failed========"
                }
            }
        }
        stage("implementation of docker scout for image vulnerability scanning"){
            steps{
                echo "========Scanning the images for vulnerabilities========"
                echo "========Scanning the frontend image========"
                sh "docker scout cves log-analysis-pipeline:frontend"
                echo "========Scanning the backend image========"
                sh "docker scout cves log-analysis-pipeline:backend"
                echo "========Scanning the ai-agent image========"
                sh "docker scout cves log-analysis-pipeline:ai-agent"
            }
            post{
                success{
                    echo "========Image vulnerability scanning completed successfully========"
                    

                }
                failure{
                    echo "========Image vulnerability scanning execution failed========"
                }
            }
        }
    }
    
}