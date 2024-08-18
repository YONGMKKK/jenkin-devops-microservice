pipeline {
	// agent any
	agent { docker { image 'maven:latest' } }
	stages {
		stage('Build') {
			steps {
				echo 'Build'
				sh 'mvn --version'
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