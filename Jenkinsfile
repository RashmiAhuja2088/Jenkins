pipeline{
	agent any
	stages{
		stage('clone'){
			steps{
				git clone https://github.com/RashmiAhuja2088/Jenkins.git
			}
		}
		stage('build'){
			steps{
				echo 'Building the code'
			}
		}
		stage('test'){
			steps{
				echo 'Testing the application'
			}
		}
		stage('deploy'){
			steps{
				echo 'deploying the application'
			}
		}
	}
}
