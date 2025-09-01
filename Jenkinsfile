//Scripted pipeline

// node {
	
// 		echo "Build"
//         echo "Test"
//         echo " Integration Test"
	
// }

//Devlarative pipeline

pipeline {
	// agent { docker { image 'maven:3.6.3'}}
	// agent { docker { image 'node:latest'}}
	agent any


	environment {
		dockerHome = tool 'myDocker'
		mavenHome =tool 'myMaven'
		PATH="$dockerHome/bin:$mavenHome/bin:$PATH"
	}

    stages {

		// stage('Docker Test') {
		// 	steps {
		// 		sh 'docker version'
		// 		sh 'docker ps'
		// 	}
		// }
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH -$PATH"
				echo "Build_num -$env.BUILD_NUMBER"
				echo "Build_id -$env.BUILD_ID"
				echo "Job_name -$env.JOB_NAME"
				echo "Build_Tag-$env.BUILD_TAG"
				echo "Build_url- $env.BUILD_URL"
			}
		}
		stage ('Compile') {
			steps {
				sh "mvn clean compile"
			}

		}

		stage('Test') {
			steps {
			   sh "mvn test"
			}
		}

		stage('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
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


