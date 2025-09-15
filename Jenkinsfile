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
          //  steps {
          //      echo "Hello world Lint"               
          //  }

             agent {
                docker {
                    image 'python:3.9-slim'
                    args '-v /tmp:/tmp'  // Optional volume mounting
                }
            }
            steps {
                script {
                    // Install dependencies if needed
                    // sh 'pip install -r requirements.txt'
                    
                    // Run Python script
                    sh 'python mainCode1.py'
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

    
        
        
    



