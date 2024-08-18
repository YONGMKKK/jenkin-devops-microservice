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
				// sh "mvn --version"
				// sh "docker version"
				sh "mvn clean compile"
			}
		}
		stage ('Unit Test') {
			steps {
				// echo "Unit Test"
				sh "mvn test"
			}
		}
		stage ('Integrateion Test') {
			steps {
				echo 'Integration Test'
				// sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
		stage('Build Docker Image') {
			steps {
				script {
					docker.build("yongmkkk/currency-exchange-devops:${env.BUILD_TAG}")
				}
			}
		}
		stage('Push Docker Image') {
			steps {
				script {
					docker.withRegistry('', 'dockerhub') {
						docker.image("yongmkkk/currency-exchange-devops:${env.BUILD_TAG}").push()
						// docker.image("yongmkkk/currency-exchange-devops:${env.BUILD_TAG}").push('latest')
					}
				}
			}
		}
	}
}