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

             steps {
                script {
                    docker.image('python:3.9-slim').inside("
                        -v ${env.WORKSPACE}:${env.DOCKER_WORKSPACE}
                        -w ${env.DOCKER_WORKSPACE}
                    ") {
                        sh '''
                            echo "Container path: ${DOCKER_WORKSPACE}"
                            python --version
                            # Your build commands
                        '''
                    }
                }
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

    
        
        
    



