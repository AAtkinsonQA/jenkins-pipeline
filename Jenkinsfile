pipeline {
  agent any
  environment {
    DB_PASSWORD=credentials('DATABASE_PASSWORD')
  }
  stages {
    stage('clone git file') {
      steps {
        sh '. ./clonecheck'
      } 
    }
    stage('install docker') {
      steps {
        sh '. ./docker-install'
      }
    }
    stage('deploy application') {
      steps {
        sh '. ./docker-deploy'
      }
    }
  }
}
