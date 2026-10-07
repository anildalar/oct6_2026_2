
pipeline{
	agent any
	stages{
		stage("State 1 - Installing Docker and Docker compose"){
			steps{
				sh 'apt update -y'
				sh 'apt upgrade -y'
				sh 'apt install sudo docker.io docker-compose -y'
				sh 'sudo service docker start'
			}
		}
		stage("State 2"){
			steps{
			   sh 'whoami'
			   sh 'docker --version'
			   sh 'docker compose version'
			}
		}
		stage("State 3 - Build the image"){
			steps{
			   sh "docker image build -t oklabs/myimag:t${BUILD_NUMBER} ."
			}
		}
	}
}
