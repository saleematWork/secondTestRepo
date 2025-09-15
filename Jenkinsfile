pipeline {
    agent any
  environment {
        DOCKER_IMAGE = 'python:3.9-windowsservercore'
        CONTAINER_WORKDIR = 'C:\\app'
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
                    image "${env.DOCKER_IMAGE}"
                    args "-v ${env.WORKSPACE}:${env.CONTAINER_WORKDIR} -w ${env.CONTAINER_WORKDIR}"
                    reuseNode true
                    }
                }
            steps {
                echo "Hello world Docker"
                bat '''
                    echo Current directory: %CD%
                    dir    
                    python --version
                    pip install --upgrade pip
                    pip install -r requirements.txt
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

    
        
        
    



