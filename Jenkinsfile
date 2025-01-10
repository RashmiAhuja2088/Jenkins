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
				echo BRANCH_NAME
				sh 'python sample.py'
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
