pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building Docker Images'
        sh 'docker build -t myflaskapp .'
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Starting docker services'
          }
        }

        stage('Run Docker Image') {
          steps {
            echo 'Running Flask app'
            sh 'docker run -p 5000:5000 myflaskapp'
          }
        }

        stage('Run Redis') {
          steps {
            echo 'Running redis'
            sh 'docker run -p 6379:6379 redis:alpine'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying Now'
      }
    }

  }
}