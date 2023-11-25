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
			echo "stage build"
		}
		stage('Test'){
			echo "stage test"
		}
		stage('Integration test'){
			echo "stage integate"
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
