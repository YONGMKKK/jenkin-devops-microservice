pipeline {
	// agent any
	// agent { docker { image 'maven:3.6.3' } }
	agent { docker { image 'node:13.8' } }
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