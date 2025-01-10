pipeline{
	agent any
	environment{
		NEW_VERSION='1.3.2'
	}
	stages{
		stage('build'){
			steps{
				echo 'Building the code'
				echo "Building version ${NEW_VERSION}"
			}
		}
		stage('test'){
			when {
    				branch 'dev'
  			}
			steps{
				echo 'Testing the application'
				echo BRANCH_NAME
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
	post{
		always{
			echo 'Job Executed'
		}
		success{
			echo 'Job Executed Successfully'
		}
		failure{
			echo 'Job Execution Failed'
		}
	}
}
