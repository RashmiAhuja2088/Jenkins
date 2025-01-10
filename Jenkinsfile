pipeline{
	agent any
	stages{
		stage('build'){
			steps{
				echo 'Building the code'
				echo "BRANCH_NAME is " + ${env.BRANCH_NAME}
			}
		}
		stage('test'){
			when {
    				branch 'dev'
  			}
			steps{
				echo 'Testing the application'
				bat "python sample.py"
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
