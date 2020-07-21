pipeline {
	agent any
	environment{
		dockerHome=too 'MyDocker'
		mavenHome=tool 'MyMaven'
		PATH="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh "mvn clean compile"
				echo "Build"
			}
		}
		stage('Test'){
			steps{
				sh "mvn test"
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps{
				sh "mvn failsafe:integration-test failsafe:verify"
				echo "Integration Test"
			}
		}
	}
	post{
		always {
			echo 'I run always'
			}
		success {
			echo 'I run on success'
			}
		failure {
			echo 'I run on failure'
			}
	}
}
