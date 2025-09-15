pipeline {
    agent any
  environment {
        // Convert Windows path to Unix path for Docker
        DOCKER_WORKSPACE = "/c${env.WORKSPACE.replace('C:', '').replace('\\', '/')}"
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/saleematWork/secondTestRepo'
            }
        }
        
        stage('Setup') {
        
            steps {
                echo "Hello world setup"              
            }
            
        }
        
        stage('Lint') {                
                agent {
                    docker {
                    image 'python:3.9-slim'
                    }
                }
            steps {
                echo "Hello world Docker"
            }
            
        }
                
                       
        


        stage('Unit Tests') {
           
            steps {
                echo "Hello world unit test"
                sh 'python mainCode1.py'
            }
        }           
        
        
        stage('Integration Tests') {
          
            steps {
                echo "Hello world Integration tests"
                sh 'python mainCode2.py'
               
            }
        }    
        
    }
}

    
        
        
    



