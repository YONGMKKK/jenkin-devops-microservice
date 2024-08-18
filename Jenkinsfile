pipeline {
	agent any
	// agent { docker { image 'maven:3.6.3' } }
	// agent { docker { image 'node:13.8' } }
	stages {
		stage('Build') {
			steps {
				// sh 'node --version'
				echo '$PATH'
				echo '$env.BUILD_NUMBER'
				echo '$env.BUILD_ID'
				echo '$env.JOB_NAME'
				echo '$env.BUILD_TAG'
				echo '$env.BUILD_URL'
			}
		}
		stage ('Test') {
			steps {
				echo 'Unit Test'
			}
		}
		stage ('IntegrateionTest') {
			steps {
				echo 'Integration Test'
			}
		}
	}
}