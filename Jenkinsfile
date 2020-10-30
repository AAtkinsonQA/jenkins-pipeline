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
        sh 'curl https://get.docker.com | sudo bash'
        sh 'sudo usermod -aG docker jenkins'
        sh 'sudo apt update'
        sh 'sudo apt install -y curl jq'
        sh 'sudo chmod +x /usr/local/bin/docker-compose'
      }
    }
    stage('deploy application') {
      steps {
        sh 'sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d'
      }
    }
  }
}
