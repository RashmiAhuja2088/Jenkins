pipeline{
	agent any
	environment {
     		env.PATH = env.PATH + ";C:\\Windows\\System32;C:\\Users\\rashm\\AppData\\Local\\Programs\\Python\\Python312"
 	}
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
				echo '$PATH'
				bat "python --version"
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
