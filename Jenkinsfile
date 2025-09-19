pipeline {
    agent any
    
  //  environment {
  //      PYTHONPATH = "${WORKSPACE}/src"
  //  }
    
    stages {
        
        stage('Checkout') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/saleematWork/secondTestRepo.git'
            }        
        }
        
        stage('Setup') {        
            steps {
                echo "Hello world setup"              
            }            
        }
        
        stage('Lint') {
            steps {
                echo "Hello world Lint"    
                script {
                    // Use official Python image with git installed (or install git in container)
                    docker.image('python:3.10-slim').inside {
                        // Install dependencies if you have requirements.txt
                        sh 'pip install --no-cache-dir -r requirements.txt || true'

                        // Run your Python script
                        sh 'python mainCode1.py'
                    }
                }
            }
        }


        stage('Unit Tests') {
           
            steps {
                echo "Hello world unit test"
            }
        }           
        
        
        stage('Integration Tests') {
          
            steps {
                echo "Hello world, Integration tests"
               
            }
        }
    }
        
    
}

    
        
        
    



