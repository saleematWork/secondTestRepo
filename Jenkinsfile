pipeline {
    agent any
    
  //  environment {
  //      PYTHONPATH = "${WORKSPACE}/src"
  //  }
    
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
                    image 'python:3.9-slim'  // Or your preferred image
                    args '-v /tmp:/tmp -w /app'
                    reuseNode true  // Reuse the workspace node
                }
            }
            steps {
                echo 'Building inside Docker container...'
                sh '''
                    echo "Running in container: $(hostname)"
                    python --version
                    pip install -r requirements.txt
                    python setup.py build
                    # Or your build commands
                    echo "Build completed in container"
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

    
        
        
    



