pipeline {
    agent any
    
  environment {
       CONTAINER_WORKDIR = '/app'
       CONTAINER_VOLUME = '/data'
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
            /*
            agent {                   
                 docker {
                    image 'python:3.9-slim'
                    args "-v ${env.WORKSPACE}:${env.CONTAINER_WORKDIR} -w ${env.CONTAINER_WORKDIR}"
                    reuseNode true
                }              
            }
            */
            
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
                           
            }
        }    
        
    }
}

    
        
        
    



