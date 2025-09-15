pipeline {
    agent any
    
  environment {
        CONTAINER_WORKDIR = '/app'
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
                    args "-v ${env.WORKSPACE}:${env.CONTAINER_WORKDIR} -w ${env.CONTAINER_WORKDIR}"
                    reuseNode true
                }
            
            }
            steps {
                echo "Hello world Docker"
               sh '''
                    echo "Running on Linux container"
                    python --version
                    pip install --upgrade pip
                    pip install -r requirements.txt
                    python -m pytest tests/ --junitxml=test-results.xml
                '''
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

    
        
        
    



