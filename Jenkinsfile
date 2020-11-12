pipeline{
	agent any
	stages{
		stage('Build') {
			steps{
				echo 'Building the docker images'
				sh 'docker build -t myflaskapp .'
			}
		}
		stage('Building'){
			parallel{
				stage('run redis'){
					steps{
						sh 'docker run -d -p 6379:6379 --name myredis redis'
					}
				}
				stage('run flask'){
					steps{
						sh 'docker run -d -p 5000:5000 --name myflaskapp_c myflaskapp'
					}
				}
			}
		}
		stage ('Testing') {
			steps{
				sh 'python test_app.py'
			}
		}
		stage ('Stop Containers') {
			steps{
				sh 'docker rm -f myflaskapp_c'
				sh 'docker rm -f redis'
			}
		}
	}
}
