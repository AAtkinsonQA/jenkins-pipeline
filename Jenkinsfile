pipeline {
  agent any
  stages {
    stage('make python file') {
      steps {
        sh 'chmod +x ./make-python.sh'
        sh './make-python.sh'
      }
      
    }
    stage('run python script') {
      steps {
        //run script with python3
        sh 'python3 helloworld.py'
      }
    }
  }
}
