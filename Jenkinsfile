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

	//agent any
	agent {
		docker {
			image 'maven:3.6.3'
			//image 'node:3.6.3'
		}
	}

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages {
		stage('build'){
			steps {
				echo "step build"
				sh 'mvn --version'
				echo "PATH - $PATH"
				echo "BUILd_NUMBER - $env.BUILd_NUMBER"
				echo "BUILd_ID - $env.BUILD_ID"
				echo "JOB_NAME - $evn.JOB_NAME"
				echo "BUILD_TAG - $evn.BUILD_TAG"
				echo "BUILD_URL - $evn.BUILD_URL"

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
