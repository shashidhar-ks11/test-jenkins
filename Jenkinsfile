// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration') {
// 		echo "Integration Test"
// 	}
// }

//Declarative

pipeline {

	agent any
	stages {
		stage('build'){
			step {
				echo "step build"
			}
		}
			
		stage('Test'){
			step {
				echo "test step"
			}
		}
		stage('Integration test'){
			step {
				echo "step integration test"
			}
		}
	}

	post {
		always{
			echo "i execute always"
		}
		success {
			echo "on success i execute"
		}
		failure {
			echo "on failure to clean up"
		}
	}
}
