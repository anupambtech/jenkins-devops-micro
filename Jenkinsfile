//Scripted pipeline approach
// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Integration Test"
// }

//Declarative pipeline
pipeline {
	agent any
	stages{
		stage('Build'){
			steps{
				echo "Build"	
			}
		}
		stage('Test'){
			steps{
				echo "Test"	
			}
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"	
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
