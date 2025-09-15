pipeline {
    agent any
    
   environment {
    // Convert Windows path to Unix path for Docker
    //    DOCKER_WORKSPACE = "/c${env.WORKSPACE.replace('C:', '').replace('\\', '/')}"
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

          stage('Build in Docker') {
            steps {
                script {
                    docker.image('python:3.9-slim').inside('-v /app:/app -w /app') {
                        // Copy files to the container's working directory
                        sh '''
                            cp -r ${WORKSPACE}/* /app/ 2>/dev/null || true
                            cd /app
                            echo "Working in: $(pwd)"
                            python --version
                            # Your build commands here
                        '''
                    }
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

    
        
        
    



