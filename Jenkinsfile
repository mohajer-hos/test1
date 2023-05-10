pipeline{

	agent any
	environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}

	stages {
	    
	    stage('gitclone') {

			steps {
				sudo git 'https://github.com/mohajer-hos/nodeapp_test.git'
			}
		}

		stage('Build') {

			steps {
				sudo sh 'docker build -t thetips4you/nodeapp_test:latest .'
			}
		}

		stage('Login') {

			steps {
				sudo sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				sudo sh 'docker push thetips4you/nodeapp_test:latest'
			}
		}
	}

	post {
		always {
			sudo sh 'docker logout'
		}
	}

}
