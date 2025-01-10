pipeline{
	agent any
	environment{
		NEW_VERSION='1.3.2'
		SERVER_CRED=credentials('Github-cred')
	}
	parameters{
		booleanParam(name: 'executeTests', defaultValue: true, description:'')
	}
	stages{
		stage('build'){
			steps{
				echo 'Building the code'
				echo "Building version "+env.NEW_VERSION
				withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'Github-cred', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
                    			echo "uname=$USERNAME pwd=$PASSWORD"
				}
				//echo "Using credentials "+env.SERVER_CRED
				//withCredentials([
				//	usernamePassword(credentialsId: 'Github-cred', usernameVariable: USER, passwordVariable: PWD)
				//]){
				//	echo "User and Pass :- ${USER} ${PWD}"
				//}
			}
		}
		stage('test'){
			when {
				expression {
    					params.executeTests == true
					BRANCH_NAME == 'dev'
				}
  			}
			steps{
				echo 'Testing the application'
				echo BRANCH_NAME
				
				bat "python sample.py"
				script {
					def data = "Hello World\nSecond line\nThird Line"
                   			writeFile(file: 'zorg.txt', text: data)
                			echo "New File created..."
				}
			}
		}
		stage('read'){
			steps {
				script {
					def content = readFile "${WORKSPACE}/zorg.txt"
					def lines = content.split("\n")[n]
					echo $lines
				}
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
