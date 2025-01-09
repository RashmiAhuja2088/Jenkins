pipeline{
	agent any
	stages{
		stage('clone'){
			steps{
				git branch: 'main'
				url: 'https://github.com/RashmiAhuja2088/Jenkins.git'
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
