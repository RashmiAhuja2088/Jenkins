pipeline{
	agent any
	stages{
		stage('build'){
			steps{
				echo 'Building the code'
			}
		}
		stage('test'){
			when {
    				branch 'dev'
  			}
			steps{
				echo 'Testing the application'
				sh 'python --version'
			}
		}
		stage('deploy'){
			when {
    				branch 'main'
  			}
			steps{
				echo 'deploying the application'
			}
		}
	}
}
