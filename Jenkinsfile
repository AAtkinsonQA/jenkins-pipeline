pipeline {
  agent any
  stages {
    stage('make python file') {
      // make file
      sh "touch helloworld.py"
      // put content in file
      sh "echo 'print("hello world")' > helloworld.py"
    }
    stage('run python script') {
      //run script with python3
      python3 helloworld.py
    }
  }
}
