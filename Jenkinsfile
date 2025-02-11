pipeline{
	agent{
		label 'EC2-Agent'
	}
	stages{
		stage('git checkout'){
			steps{
				git 'https://github.com/siddudev/Java-App.git'
			}
		}
		stage('stop running containers'){
			steps{
				sh 'docker-compose down'
			}
		stage('clean docker'){
			steps{
				sh 'echo y | docker system prune -a'
			}
		}
		stage('create and execute'){
			steps{
				sh 'docker-compose up -d'
			}
		}
		stage('docker clean'){
                        steps{
                                sh 'echo y | docker system prune -a'
                        }
                }
	}
}

