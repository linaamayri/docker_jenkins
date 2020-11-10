pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            echo 'We are in Build Stage'
          }
        }

        stage('Build2') {
          steps {
            echo 'We are in Build 2 stage'
          }
        }

      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'We are in test Stage'
          }
        }

        stage('Test 2') {
          steps {
            echo 'We are in test 2 stage'
          }
        }

      }
    }

    stage('Finish') {
      steps {
        echo 'We are in rg=he Finishing Stage'
      }
    }

  }
}