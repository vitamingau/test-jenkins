
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
					sh 'docker build -t phuphan/test-jenkins-pipeline:v1 .'
					sh 'docker push phuphan/test-jenkins-pipeline:v1'
				}
			}
		}
		stage('ssh server'){
			sshagent(['979f0abc-9a4c-424d-b941-8b55ee3f95f3']) {
    			sh 'ssh -o StrictHostKeyChecking=no -l root 34.126.105.248 touch test.txt'
			}
		}
	}		
}