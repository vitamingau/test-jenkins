
pipeline {
	agent any 
	stages {
		stage('Clone') {
			steps {
				git 'https://github.com/vitamingau/test-jenkins.git'	
			}
		}
		stage('Clone stage'){
			steps {
				withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
					sh 'docker build -t phuphan/test-jenkins-pipeline:v10'
					sh 'docker push -t phuphan/test-jenkins-pipeline:v10'
				}
			}
		}
	}		
}