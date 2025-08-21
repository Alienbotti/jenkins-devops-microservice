//Scripted pipeline

// node {
	
// 		echo "Build"
//         echo "Test"
//         echo " Integration Test"
	
// }

//Devlarative pipeline

pipeline {
	agent {docker {image 'maven:3.6.3'}} 
	environment {
		DOCKER_HOST = "tcp://host.docker.internal:2375"
	}
    stages {
		stage('Docker Test') {
			steps {
				sh 'docker version'
				sh 'docker ps'
			}
		}
		stage('Build') {
			steps {
				sh 'mvn --version'
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


