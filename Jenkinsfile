pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
                sh 'wget -q --spider http://localhost:5000
	
                    if [ $? -eq 0 ]; then
                      echo "Online"
                      break
                    else
                      echo "Offline"
                      sleep 5
                    fi'
            }
        }
    }
}
