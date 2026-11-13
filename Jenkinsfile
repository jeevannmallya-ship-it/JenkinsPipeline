pipeline{ 
  agent any 
  stages { 
     stage('Checkout') { 
        steps{ 
          checkout scm 
        }
     }
    stage('Build'){
      steps {
        echo 'Checking Python application'
        bat 'python -m py_compile app.py'
      }
    }
    stage('Test'){
      steps {
        echo 'Executing automated Tests'
         bat 'python -m unittest app'
      }
    }
    stage('Run Application'){
      steps{
        bat 'python app.py'
      }
    }
  }
  post {
    success {
      echo 'CI Pipeline completed Successfully'
    }
    failure {
      echo 'CI Pipeline failed'
    }
  }
}
      
