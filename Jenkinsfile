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
		stage('Checkout'){
			steps {
				echo "step build"
				sh 'mvn --version'
				echo "PATH - $PATH"
				echo "BUILd_NUMBER - $env.BUILd_NUMBER"
				echo "BUILd_ID - $env.BUILD_ID"
				//echo "JOB_NAME - $evn.JOB_NAME"
				echo "BUILD_TAG - $evn.BUILD_TAG"
				//echo "BUILD_URL - $evn.BUILD_URL"

			}
		}

		stage('Compile'){
			steps{
				echo "mvn clean compile"
				sh 'mvn clean compile'
			}
		}
			
		stage('Test'){
			steps {
				echo "test step - skipping"
				//sh 'mvn test'
			}
		}
		stage('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}

		stage('Package') {
			steps {
				sh "mvn package -DskipTests"
			}
		}

		stage('build docker') {
			steps{
				script {
					docker_image = docker.build("currency-exchange-devops:${env.BUILD_TAG}")
				}
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
