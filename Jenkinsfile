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