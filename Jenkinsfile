pipeline{
	agent any
	environment{
		NEW_VERSION='1.3.2'
		SERVER_CRED=credentials('Github-cred')
	}
	stages{
		stage('build'){
			steps{
				echo 'Building the code'
				echo "Building version "+env.NEW_VERSION
				//echo "Using credentials "+env.SERVER_CRED
				withCredentials([
					usernamePassword(credentialsId: 'Github-cred', usernameVariable: USER, passwordVariable: PWD)
				]){
					echo "User and Pass :- ${USER} ${PWD}"
				}
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
