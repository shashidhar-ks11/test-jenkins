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
			steps {
				echo "step build"
			}
		}
			
		stage('Test'){
			steps {
				echo "test step"
			}
		}
		stage('Integration test'){
			steps {
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
