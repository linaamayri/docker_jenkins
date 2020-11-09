pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building Docker Images'
        sh 'docker build -t myflaskapp .'
        sh 'docker run -p 5000:5000 myflaskapp'
      }
    }

    stage('Test') {
      steps {
        echo 'Running Python tests'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying Now'
      }
    }

  }
}