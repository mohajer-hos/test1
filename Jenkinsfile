pipeline{

	agent any
	environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}

	stages {
	    
	    stage('gitclone') {

			steps {
				 git 'https://github.com/mohajer-hos/nodeapp_test.git'
			}
		}

	}


}
