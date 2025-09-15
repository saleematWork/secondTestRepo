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
                    image 'myapp'                
                }
            }
            steps {
              echo "docker image"
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

    
        
        
    



