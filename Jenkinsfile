//Scripted pipeline

// node {
	
// 		echo "Build"
//         echo "Test"
//         echo " Integration Test"
	
// }

//Devlarative pipeline

pipeline {
	// agent { docker { image 'maven:3.6.3'}}
	agent { docker { image 'node:latest'}}

    stages {
		// stage('Docker Test') {
		// 	steps {
		// 		sh 'docker version'
		// 		sh 'docker ps'
		// 	}
		// }
		stage('Build') {
			steps {
				sh 'node --version'
				echo "Build"
			}
		}

		stage('Test') {
			steps {
				echo "Test"
			}
		}

		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	}

	post {
		always {
			echo "I run always"
		}

		success {
           echo "I run when you are successfull"
		}

		failure {
			echo "I run when you fail"
		}
	}
}


