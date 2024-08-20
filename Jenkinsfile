// //Scripted -> Groovy Script

// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 		echo "Integration Test"
// 	}
// }


// Declarative 

pipeline{

	agent any

	// agent { docker { image 'maven:3.9.8' } } 

	// agent { docker { image 'node:22.6' } }

	environment {
		dockerHome = tool 'abDocker'
		mavenHome = tool 'abMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages{

		stage('Checkout'){

			steps{

				sh 'mvn --version'
				sh 'docker --version'
				echo "Build"
			}
		}

		stage('Compile'){

			steps{

				sh 'mvn clean compile'
			}
		}

		stage('Test'){

			steps{

				sh 'mvn test'
			}
		}

		stage('Integration Test'){

			steps{

				sh 'mvn failsafe:integration-test failsafe:verify'
			}
		}
	} 
	
	post {

		always{
			
			echo "I'm running successfully so far."
		}

		success{

			echo "I ran successfully."
		}

		failure{

			echo "oops, I failed in running. Kindly, check the issue!"
		}
	}
}