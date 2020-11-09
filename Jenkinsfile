pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
                sh 'wget -q --spider http://localhost:5000'
            }
        }
    }
}
