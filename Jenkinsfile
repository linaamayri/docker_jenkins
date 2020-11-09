pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
                sh 'sudo docker-compose up'
            }
        }
    }
}
