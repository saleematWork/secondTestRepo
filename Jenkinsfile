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
                    def workspacePath = pwd().replaceAll('\\\\', '/').replaceFirst('^([A-Za-z]):', '/$1').toLowerCase()
                    // Converts C:\path\to\workspace to /c/path/to/workspace

                    docker.image('python:3.10-slim').inside("-v ${workspacePath}:/app -w /app") {
                        //sh 'pip install -r requirements.txt || true'
                        sh 'mainCode1.py'
                        
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

    
        
        
    



