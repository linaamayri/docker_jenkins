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
						sh 'docker run -d -p 6379:6379 redis'
					}
				}
				stage('run flask'){
					steps{
						sh 'docker run -d -p 5000:5000 myflaskapp'
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
				sh 'docker container rm -f $(docker container ls -qa)'
			}
		}
	}
}
