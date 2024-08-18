pipeline {
	agent any
	// agent { docker { image 'maven:3.6.3' } }
	// agent { docker { image 'node:13.8' } }

	environment {
		dockerHome = tool "myDocker"
		mavenHome = tool "myMaven"
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages {
		stage('Build') {
			steps {
				sh "mvn --version"
				sh "docker version"
				// sh "mvn clean package"
			}
		}
		stage ('Unit Test') {
			steps {
				echo "Unit Test"
				// sh "mvn test"
			}
		}
		stage ('Integrateion Test') {
			steps {
				echo 'Integration Test'
			}
		}
	}
}