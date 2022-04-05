//Scripted pipeline approach
// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Integration Test"
// }

//Declarative pipeline
pipeline {
	agent any
	// agent{ 
	// 	docker { image 'node:current-alpine3.15'}
	// }
	environment{
		dockerHome= tool "my-docker"
		mavenHome=tool "my-maven"
		PATH="$dockerHome/bin:mavenHome/bin:$PATH"
	}
	stages{
		stage('checkout'){
			steps{
				sh "mvn --version"
				sh "docker --version"
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "JOB_NAME - $env.JOB_NAME"
			}
		}
		stage('Build'){
			steps{
				sh "mvn clean build"	
			}
		}

		stage('Unit Test'){
			steps{
				sh "mvn test"	
			}
		}
		stage('Integration Test'){
			steps{
				sh "mvn failsafe:integration_test failsafe:verify"	
			}
		}
	}
	post{
		always{
			echo "I am awesome!!!"
		}
		success{
			echo "I run when you successful!!!"
		}
		failure{
			echo "I run when you failes!!!!"
		}
	}
		
}
